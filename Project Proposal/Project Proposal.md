# Project Proposal - ERPNext
## Hypothetical Operational Environment
This is an ERP, so it’s basically responsible for consolidating company data and providing standardized functionality needed in standard business scenarios (i.e. payroll, time management, employee data collection/storage/edits/protection, etc.) 
## System Engineering View
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Project%20Proposal/System%20Engineering%20View.png)  
The system of interest is the ERPNext system as it is the bridge between multiple elements of a business. It contains sensitive information relating to user logins, vendors, and customers. It also exchanges data with other applications used by the company it’s implemented at. For our Systems Engineering View, we made a mockup showing the hypothetical interactions ERPNext would have if implemented at a typical company.
## Threats
* Insider threats that could lead to damage of the system, and disclosure of sensitive information or company secrets.
* Identity spoofing is a threat of a user obtaining login information of another user and acting as that person in the system.
* Elevation of privilege would allow a lower access user to gain higher access levels and see information they are unintended to.
* ERP systems store a lot of sensitive information about customers, users, and vendors. Any unauthorized disclosure of the information is a huge threat.
## Security Features
* User account control
* Possible two-factor authentication implementation 
* Automated account auditing
* Login attempt limit and auditing
* Protection against some forms of XSS
* Password encryption at rest
* Backup capacity
* SSL certificate usage for any websites created
## Team Motivation
We were searching for a software that was both interesting to explore, and also rich with potential security improvements across multiple parameters. ERPNext can span across many systems in a company so it carries security issues of protecting any sensitive information that system has given to ERPNext. Erik and Jake both have previous work with SAP and as this software is the “open source alternative to SAP”, the topic of an ERP system is familiar.
## Project Description
ERPNext is an open source enterprise resource planning software. It is an open source alternative to SAP, the world's largest ERP software. ERPNext encourages contributions from anyone looking to improve their software, documentation and community. They have a strict code of conduct for contributors and community members to encourage a harassment-free space for anyone. ERPNext's GitHub has over 12,000 pull requests with 30 in the last week. The community is active and is constantly improving the software. ERPNext covers a large array of modules as it is meant to span across all business processes. The core modules are Accounts, Stock, CRM, Selling, Buying, Human Resources, Projects, Support, Asset, & Quality. They are industry specific modules relating to Manufacturing, Education, Healthcare, Agriculture, Non-Profit, & Hospitality. ERPNext is used by over 5000 companies worldwide. ERPNext is written with the Frappe Framework, a full-stack web app framework built with Python & JavaScript. Full [documentation](https://docs.erpnext.com/) and [user manual](https://docs.erpnext.com/docs/user/manual/en) can be found here.
## Licenses
ERPNext code is under the GNU General Public License v3.
The documentation is licensed under Creative Commons CC-BY-SA-3.0.
The copyright and trademarks for the name and logo is owned by Frappe Technologies Pvt Ltd (Frappe) and Contributors.
## Security-Related History
* A number of user access control issues were closed between May 2017 - April 2020.  
* Community information regarding two-factor authentication in 2017 was added. 
* Dormant account notifications were added to the better on boarding milestone.  
* Login attempt limits added on commit 0a56d63 on Aug. 11, 2018.  
* Some XSS protections added upon as part of Pull 4560.  
* Vulnerabilities regarding the vulnerabilities that affect acorn, minimist, and svjsl regarding CVE-2020-7598 as part of Pull #20937.
## Repository Link
[https://github.com/eeiler/Team-8-ERPNext](https://github.com/eeiler/Team-8-ERPNext)
## Teamwork & Issues
Our team faced moderate timing and communication issues initially. We combatted this by starting a Discord channel and scheduling weekly meetings, as well as additional working meetings, which were made possible by sharing our weekly schedules. 
We use the weekly meetings to check up with each other and discuss what work needs to be done, and the working meetings to actually accomplish any necessary group work. 
We also divy up work that can be completed individually during these meetings by playing to our individual strengths and schedules. 
Moving forward, keeping these lines of communication open and being honest about our level of comfort with certain tasks is the path we see to completing a successful project for this course.
## Team 8
[Erik Eiler](https://github.com/eeiler)  
[Jake Ferrin]()  
[Alexander Bladow]()  
