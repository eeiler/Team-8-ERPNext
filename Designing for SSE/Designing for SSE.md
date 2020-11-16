# Designing for Software Security Engineering
## Threat Modeling
### Data Flow Diagram for ERPNext
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Designing%20for%20SSE/TMT.png)
[HTML Threat Model Report](https://eeiler.github.io/Team-8-ERPNext/Designing%20for%20SSE/report.htm)
## Observations
### Denial of Service
Threats numbers from the above report: 1, 9, 10, 31, 50, 57, 65  
Observations:
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
