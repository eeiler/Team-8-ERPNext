# Designing for Software Security Engineering
## Threat Modeling
### Data Flow Diagram for ERPNext
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Designing%20for%20SSE/TMT.png)
[HTML Threat Model Report](https://eeiler.github.io/Team-8-ERPNext/Designing%20for%20SSE/report.htm)
## Observations
### Denial of Service
Potential Interruptions (Threats: 1, 9)  
One threat we could face are external players using some method to block credential and data exchanges between our users and our data stores. Mitigating this could happen a few ways, but one necessary function we need is the ability to have admins who can do things like resetting access or opening a new secure place for the exchange to occur in. Additionally, automated monitoring of data being retrieved under which credentials via reports or audit logs could be useful in checking to make sure the only interactions coming at the databases are coming from secure sources. Furthermore, running a corporate VPN on machines to keep external players out of them would also do a lot to combat this issue.

Crashing and Performance Issues (Threats: 10, 50, 57)  
To combat unexpected crashes and performance issues, we need two things. First off, system admins need to be able to restart the system both locally and remotely, including the option for a force restart. Second, we need an error log so those same admins can easily troubleshoot the issues causing the crashing and work to mitigate them moving forward.

Excessive Resource Consumption (Threats: 31, 65)  
We do not currently have a way to mitigate this issue. A potential solution could be imposing some kind of system request limit on every user (i.e. reports are limited to 10,000 employee records, etc.) A limit like this could lead to excessively throttling users and losing usability, so having a way to manually override it from an admin level wouldn’t be a bad idea. Imposing a limit also adds security to the threat of malicious resource consumption from external players in that they can’t ever get all of our data all at once. Furthermore, making sure all requests to any of the data stores utilized timeout so nothing can go on pulling data forever. Multiple requests like this running would surely shut down our system.

### Repudiation
Threats numbers from the above report: 2, 12  
Observations: These repudiation threats are both during the Employees interaction with the ERPNext system. In the [documentation](https://docs.erpnext.com/docs/user/manual/en), we were not able to locate a logging system for employee login attempts. The creation of a system login log would enable the company to track the interaction and ensure proper function of the process. The log would also give insight into the security mechanism function, ensuring that it is working properly and showing any patterns that may need to be planned for. This log could also be used to track employee logins to keep track of who is logged in and when.

Threats numbers from the above report: 38, 51  
Observations: We did not find documentation on any logging happening by ERPNext at the authentication of user logins. Logging the interactions of the authentication process and the data store would ensure that nothing is being written. This credentials data store will need to be written onto only when a new employee is added. That should be specifically handled by and administrator and enforced by User Access Controls of which ERPNext system has. So logging any interaction would ensure correct system function and make sure only valid users are being written into the data store.
### Spoofing
Threats numbers from the above report:  17, 19
Observations:
### Escalation of Priviledge
Threats numbers from the above report:  20
Observations:
## Teamwork
[Team Project Board](https://github.com/eeiler/Team-8-ERPNext/projects/4)   
For this deliverable we all worked together on the data flow diagram as it was only one big diagram. We screenshared in a Discord call for ease of communication. We then went through each threat identified by TMT and talked through the correct current state of the threats. The threats that needed investigation were identified, separated into categories, and divided up for each of us to write our observations. Erik handled the Repudiation category; Jake handled the Denial of Service category; Alex handled the Spoofing and Escalation of Privilege category. This allowed us to fairly distribute the work while still having communication on the observations of the TMT. In terms of time management, we were slow this week, but planned work time for us all to work together to get the deliverable handled. We aim to be better prepared for the next deliverable, especially utilizing the instructor meeting more effectively.
