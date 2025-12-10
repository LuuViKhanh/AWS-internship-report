---
title: "Week 12 Worklog"
date: 2025-09-09
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---



### Week 12 Objectives:

* Continue developing and perfecting the final course project.
* Coordinate with database and frontend teams to integrate the system.
* Resolve technical errors related to data types and configuration.
* Handle CORS issues in API integration.
* Write workshop and prepare project documentation.
* Attend AWS Cloud Mastery Series event on Security Pillar.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Continue working on project <br>&emsp; + Coordinate with database team to connect data <br>&emsp; + Encountered error: java.lang.NumberFormatException: Character N is neither a decimal digit number, decimal point, nor "e" notation exponential mark <br>&emsp; + This error was due to null values in integer fields <br>&emsp; + Fixed database by removing null values <br>&emsp; Error resolved <br> - Encountered error: java.lang.IllegalArgumentException: Could not resolve placeholder 'app.jwt.secret' in value "${app.jwt.secret}" <br>&emsp; + Added environment variable <br>&emsp; Error resolved                                                                                                   | 24/11/2025 | 24/11/2025      |  |
| 3   | - Continue working on project <br>&emsp; + Coordinate with frontend team to call API <br>&emsp; + Encountered error: java.lang.IllegalArgumentException: Boolean string was not 'true' or 'false': 1 <br>&emsp; + Fixed by changing boolean to integer <br> Error resolved                                              | 25/11/2025 | 25/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Continue working on project <br>&emsp; + Coordinate with frontend team to call API <br>&emsp; + Encountered error: has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource <br>&emsp; + Fixed on frontend side <br>&emsp; + Added to OPTIONS method, Access-Control-Allow-Methods -> 'GET,POST,PUT,DELETE,OPTIONS' <br> Error resolved | 26/11/2025 | 26/11/2025      | [CORS policy error: No 'Access-Control-Allow-Origin' header](https://www.youtube.com/watch?v=PNtFSVU-YTI) |
| 5   | - Continue working on project <br>&emsp; + Write workshop <br>&emsp; + Push backend to GitHub                            | 27/11/2025 | 27/11/2025      |  [workshop](https://github.com/Huntrot/Group7_Workshop.git) <br>[backend](https://github.com/LuuViKhanh/Group7_Workshop_BE.git) |
| 6   | - Attend AWS Cloud Mastery Series #3 - AWS Well-Architected Security Pillar event                                                                                     | 28/11/2025 | 28/11/2025      | [AWS Cloud Mastery Series #3](https://luma.com/0nl16e1p?tk=OBSrJI) |


### Week 12 Achievements:

* **Resolved NumberFormatException and JWT configuration errors:**
  * Coordinated with database team to connect data
  * Encountered error: java.lang.NumberFormatException: Character N is neither a decimal digit number
  * Discovered error was due to null values in integer fields
  * Fixed database by removing null values
  * Encountered error: Could not resolve placeholder 'app.jwt.secret'
  * Added environment variable to resolve JWT configuration issue
  * Successfully resolved all errors and system operates stably

* **Coordinated with frontend team and resolved API errors:**
  * Coordinated with frontend team to call API
  * Encountered java.lang.IllegalArgumentException error regarding Boolean data type again
  * Fixed by changing boolean to integer to ensure consistency
  * Successfully resolved data type mismatch issue
  * Enhanced debugging skills and integration error handling

* **Handled CORS issues in API Gateway:**
  * Continued coordinating with frontend team to call API
  * Encountered CORS policy error: No 'Access-Control-Allow-Origin' header
  * Fixed on frontend side to handle CORS
  * Added to OPTIONS method: Access-Control-Allow-Methods -> 'GET,POST,PUT,DELETE,OPTIONS'
  * Completely resolved CORS issue
  * Learned how to configure CORS for API Gateway

* **Wrote workshop and managed source code:**
  * Wrote workshop for the project to guide others
  * Pushed backend code to GitHub for version management
  * Organized and documented the entire project
  * Prepared documentation for demo and handover
  * Enhanced technical documentation writing skills

* **Attended event and learned about Security:**
  * Attended AWS Cloud Mastery Series #3 event
  * Learned about AWS Well-Architected Security Pillar
  * Learned about best practices for security on AWS
  * Applied security knowledge to practical projects
  * Updated knowledge about security compliance and governance

* **Improved teamwork and problem-solving skills:**
  * Worked effectively with multiple teams (database, frontend)
  * Quickly resolved complex technical issues
  * Enhanced debugging and troubleshooting skills
  * Developed communication and project coordination skills
