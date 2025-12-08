---
title: "Blog 2"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---



# **Implement a USDC bridge on AWS**

By **Corey Cooper** and **Guillaume Goutaudier** on 09 JUN 2025 in **Advanced (300)**, **AWS Step Functions**, **Blockchain**, **Technical How-to**

## **Introduction**

**Stablecoins** offer significant advantages in the **crypto space**. They provide price stability and can serve as a reliable medium of exchange, store of value, or bridge between the **fiat** and **crypto** ecosystems. The ability to transfer **stablecoins** across multiple **blockchains** further enhances their utility by improving **cross-chain interoperability** and letting users take advantage of the strengths of different networks.

**Circle** is a financial platform that offers regulated **stablecoins**, tokenized funds, developer services, and liquidity services to help businesses deliver the future of finance across multiple **blockchains**. **Circle** is widely known for its prominent dollar **stablecoin**, **USDC**.

With **Circle's** recent release of its interoperability service, **CCTP (Cross-Chain Transfer Protocol) V2**, we wanted to explore how **USDC** could be transferred between multiple chains using a **serverless** architecture on **AWS**.

In this post, we describe and deploy such an architecture. We focus on the **backend** components, using the **Quickstart: Cross-Chain USDC Transfer** from the **Circle** developer documentation as a reference. We illustrate how to use **serverless AWS services** such as **AWS Lambda** and **AWS Step Functions** to implement **onchain workflows**.

This solution is particularly valuable for businesses building **multi-chain DeFi platforms**, **NFT marketplaces**, or **cross-border payment systems**. By using **AWS serverless services**, developers can reduce infrastructure complexity, speed up integration of **cross-chain transfers**, and maintain high availability and scalability with minimal operational overhead.

## **Solution overview**

The high-level architecture of the solution is shown in the following diagram.

![USDC Bridge Architecture](/images/3-BlogsTranslated/blog2/1.png)

The **workflow** is implemented as a **Step Functions state machine** that orchestrates the execution of multiple **Lambda functions**. These **Lambda functions** interact with the source and target networks, the **Circle Attestation Service** (which observes and verifies the **burn** activity on the source chain), and use **AWS Secrets Manager** to store the **private keys** of the account from which we want to transfer **USDC**.

**Step Functions** offers several benefits, including built-in error handling and **timeouts**, direct integration with **AWS services**, built-in state management and **workflow** progress tracking, and real-time and auditable **workflow** execution history.

The following figure illustrates the **state machine workflow** for a **CCTP V2 Fast Transfer**.

![Step Functions Workflow](/images/3-BlogsTranslated/blog2/2.png)

The **workflow** implements the required steps for using **CCTP V2** (for a thorough understanding of these steps, refer to the **CCTP developer documentation**):

1. Validate the input variables.
2. Generate a **bytes32** representation of the address where the **USDC** are to be sent.
3. Approve the spending of the required amount of **USDC** on the **TokenMessengerV2 smart contract**.
4. **Burn USDC** on the source network using the **TokenMessengerV2 smart contract**.
5. Retrieve a **message** and **attestation** from the **Circle Attestation Service**.
6. **Mint USDC** on the target network using the **MessageTransmitterV2 smart contract** (getting a new **attestation** if required).

At the time of writing, **CCTP V2** supports **Ethereum**, **Avalanche**, **Base**, **Linea**, and **Arbitrum** networks. We therefore focus the implementation on **EVM-compatible blockchains**.

The **workflow** is implemented on **test networks** using endpoints from **Public Node**. For **production** use, the following should be considered (at the minimum):

- The management of the **private keys** should be given additional considerations. Refer to **How to sign Ethereum EIP-1559 transactions using AWS KMS** to learn how additional **AWS security services** such as **AWS Key Management Service (AWS KMS)** can improve your security posture. **Multi-party authorization** can also be implemented for higher-value transfers.

- You might want to run your own **nodes**. You can refer to **AWS Blockchain Node Runners** for **node** deployment blueprints and to the **AWS Nitro Enclaves for running Ethereum validators** blog post series for detailed instructions on how to sign transactions inside a **Nitro enclave**.

- You should attach the **Lambda functions** to a **VPC**. Refer to **Giving Lambda functions access to resources in an Amazon VPC** for more details.

- For each step of the **workflow**, you should review all possible types of failure and confirm how you want to handle them. For example, the **uptime** and availability of the **CCTP service** are designed to be similar to how the existing **minting services** operate today, but you should still define how to handle delayed transactions or temporary unavailability of the **Attestation Service**.

- The solution can also be integrated into a wider decentralized application. For example, you can use **Amazon Simple Notification Service (Amazon SNS)** to send notifications to end-users, and use **Amazon EventBridge** to trigger additional post-transfer actions.

To deploy this solution, we use the following **AWS CloudFormation template**. The template requires a **private key** as input parameter, so we generate one before deploying the template. We then test an actual **USDC** transfer from **Ethereum** to **Base**.

## **Prerequisites**

To implement this solution, you should have an **AWS account** with the appropriate permissions.

## **Create a private key**

There are many different ways to generate a **private key**. For this post, we use the **Python Web3 library** from **AWS CloudShell**. To generate a **private key** and associated address, connect to **CloudShell** and run the following command:

```bash
pip install web3 && \
python -c "from web3 import Web3; w3 = Web3(); acc = w3.eth.account.create(); print(f'PRIVATE_KEY={acc._private_key.hex()}; ADDRESS={acc.address}')"
```

Execute the output of the previous command to record the **PRIVATE_KEY** and **ADDRESS**.

## **Deploy the CloudFormation template**

From the same **CloudShell** session, run the following command to deploy the **CloudFormation template**:

```bash
aws cloudformation create-stack --region us-east-1 --stack-name 'USDC-Bridge' --template-url 'https://aws-blogs-artifacts-public.s3.us-east-1.amazonaws.com/artifacts/WEB3-2/USDC-Bridge-CloudFormation-Template.yml' --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=PRIVATEKEY,ParameterValue=$PRIVATE_KEY
```

## **Test the solution**

To be able to transfer **USDC** from one network to the other, you need **native tokens** (**ETH** for **Ethereum**, for example) from the source and target networks (so you can pay for the **gas fees**) and **USDC** on the source network (so you have **USDC** to transfer in the first place). Because we deployed the solution for **testnets**, those can be obtained from **faucets**. The following is a non-exhaustive list of **faucets** you may want to use:

- **USDC Testnet Faucet** from **Circle**
- **Sepolia Faucets** from **Chainlink**
- **Ethereum Sepolia Faucet** from **Alchemy**
- **Multi-Chain Faucet** from **QuickNode**
- **Chainstack multi-chain faucet**
- **Free testnet faucets** from **thirdweb**

In this section, we illustrate how we transferred **USDC** from **Ethereum** to **Base**, but you can experiment with other networks. To execute the **Step Functions state machine**, we can prepare the following input parameters:

```json
{
  "source_address": "<replace_with_public_address_from_previous_step>",
  "target_address": "<replace_with_public_address_from_previous_step>",
  "amount": 10000,
  "max_fee": 100,
  "source_domain": "0",
  "target_domain": "6"
}
```

We use the same source and target addresses, but you can use a different target address. Additionally, this solution is using **Fast Transfer** (for more details on **Fast Transfers**, refer to **CCTP product fee schedule**).

To execute the **Step Functions state machine**, complete the following steps:

1. On the **Step Functions console**, select the **USDC_Bridge state machine**.
2. Choose **Start execution**.
3. Insert the **JSON document** you previously prepared.
4. Choose **Start execution**.

If all goes well, you should see the different steps of the **state machine** being successfully executed until the end of the **CCTP V2 Fast Transfer workflow**.

![State Machine Execution](/images/3-BlogsTranslated/blog2/3.png)

If something goes wrong, you will be able to visually identify at which step the issue occurred, inspect the input and output of the step, and review the logs of the **Lambda functions**. **Step Functions** also provides the ability to resume the execution of the **workflow** after an initial failure, and integrates with **Amazon CloudWatch** for enhanced observability and alerting.

After the **workflow** is successfully executed, you can confirm that **USDC** has been successfully transferred, and review the **smart contracts** executions using **block explorers**. In particular, you can note the **transaction hash** from the output of the **Mint USDC** step, and confirm that the logs of this transaction indicate that new **USDC** have been **minted**, as shown in the following screenshot.



## **Clean up**

From **CloudShell**, run the following command to clean up your resources:

```bash
aws cloudformation delete-stack --stack-name 'USDC-Bridge'
```

## **Conclusion**

In this post, we showed you how you can use **CCTP V2**, **Lambda**, **Step Functions**, and **Secrets Manager** to implement a **serverless** solution to transfer **USDC** on the **backend** of **onchain applications**. You can expand this solution and integrate it into a wider set of **AWS tools** and services, making it an ideal platform for running **onchain workloads**. We encourage you to experiment on your own and share your feedback.

## **About the authors**

### **Corey Cooper**


**Corey** is a developer at **Circle** who loves basketball and is a lifelong **Lakers** fan from **Atlanta**, with a career spent building enterprise and payment technology. With over 15 years of experience as a solutions engineer, he brings a mix of technical depth, business insight, and hands-on leadership to product launches, **go-lives**, and scalable platform builds.
![Corey Cooper](/images/3-BlogsTranslated/blog2/4.png)
### **Guillaume Goutaudier**
**Guillaume** is a **Sr Enterprise Architect** at **AWS**. He helps companies build strategic technical partnerships with **AWS**. He is also passionate about **blockchain technologies**, and is a member of the **Technical Field Community for blockchain**.
![Corey Cooper](/images/3-BlogsTranslated/blog2/5.png)