# Project Proposal - ERPNext
## Hypothetical Operational Environment
This is an ERP, so it’s basically responsible for consolidating company data and providing standardized functionality needed in standard business scenarios (i.e. payroll, time management, employee data collection/storage/edits/protection, etc.) 
We’re using Kiewit as the hypothetical client reference for this software. Beyond standard business practices, Kiewit will expect a drastic amount of integrations with both in-house and external software, meaning this software will be responsible for on-going security around the data exchanged between the applications used by the company. 
## System Engineering View
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/System-of-Interest.png)  
The system of interest is the ERPNext system as it is the bridge between multiple elements of a business. It contains sensitive information relating to user logins, vendors, and customers. It also exchanges data with other applications used by the company it’s implemented at. For our Systems Engineering View, we made a mockup showing the hypothetical interactions ERPNext would have if implemented at Kiewit. Kiewit uses many applications from its subsidiary, InEight, which are partially developed in-house, and externally. They also use other in-house software to manage everything from payroll and time, to contracts and construction projects. Beyond that, fully external software, namely the Microsoft Suite, is also utilized and integrated with all of the aforementioned applications.
## Threats
* Insider threats that could lead to damage of the system, and disclosure of sensitive information or company secrets.
* Identity spoofing is a threat of a user obtaining login information of another user and acting as that person in the system.
* Elevation of privilege would allow a lower access user to gain higher access levels and see information they are unintended to.
* ERP systems store a lot of sensitive information about customers, users, and vendors. Any unauthorized disclosure of the information is a huge threat.
## Security Features
*Insert*
## Team Motivation
We were searching for a software that was both interesting to explore, and also rich with potential security improvements across multiple parameters. ERPNext can span across many systems in a company so it carries security issues of protecting any sensitive information that system has given to ERPNext. Erik and Jake both have previous work with SAP and as this software is the “open source alternative to SAP”, the topic of an ERP system is familiar.
## Project Description
ERPNext is an open source enterprise resource planning software. It is an open source alternative to SAP, the worlds largest ERP softwware. ERPNext encourages contributions from anyone looking to improve their software, documentation and community. They have a strict code of conduct for contributors and community members as to encourage a harrasment-free space for anyone. ERPNext's GitHub has over 12,000 pull requests with 30 in the last week. The community is active and is constantly improving the software. ERPNext covers a large array of modules as it is meant to span across the entire businesses processes. The core modules are Accounts, Stock, CRM, Selling, Buying, Human Resources, Projects, Support, Asset, & Quality. They are industry specific modules relating to Manufacturing, Education, Healthcare, Agriculuture, Non-Profit, & Hospitalilty. ERPNext is used by over 5000 companies worldwide. ERPNext is written with the Frappe Framework, a full-stack web app framework built with Python & JavaScript. Full [documentation](https://docs.erpnext.com/) and [user manual](https://docs.erpnext.com/docs/user/manual/en) can be found here.
## Licenses
ERPNext code is under the GNU General Public License v3.
The documentation is licensed under Creative Commons CC-BY-SA-3.0.
The copyright and trademarks for the name and logo is owned by Frappe Technologies Pvt Ltd (Frappe) and Contributors.

## Security-Related History
*Insert*
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
