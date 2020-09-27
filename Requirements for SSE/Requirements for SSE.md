## Case 1
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/Email%20Rec%20Case.png)  
Employees using the ERPNext software must be able to communicated through email both internally and externally.  
Email is a commonly exploited area of business for malicious attackers. The misuse case is the malicious email sender trying to spam the employee with emails that could have dangerous files inside, or be phishing for employee information.

ERPNext does use a configurable attachment limit to prevent large email sizes being used as a email DoS bomb.
ERPNext recommends for things like spam filtering, that it be done by the mail server provider external of ERPNext.
ERPNext allows for pdfs of documents to be attached to emails sent through it. Which would be received by other employees.

ERPNext is clear in the [https://docs.erpnext.com/docs/user/manual/en/setting-up/email](email section) of the user manual of certain security requirements that should be handled outside of this software, such as spam filtering, SSL, and TSL. They do provide things such as attachment limiting to prevent the DoS of the ERP system.
The security provided is little by ERPNext as the pass the responsibility to the mail server provider, but something they should add is a notifier flag in the email subject when it is received from outside the company. An option to notify of an important document on internal emails also would add good clarity to the email system
## Case 2
![]()  

## Case 3
![]()  

## Case 4 
![]()  

## Teamwork
[Team Project Board](https://github.com/eeiler/Team-8-ERPNext/projects/1)  
We decided to get started early in the week on the use cases. This allowed us to use our team checkup to review how the cases should be done. We struggled to get a strong grasp on the cases at first, so we asked questions in a meeting with our professor and studied the lecture again before meeting to work on the cases again. We plan to continue starting early in the week, so we can get any questions and feedback at our checkup meetings. We also ran into scheduling issues this week. There are a lot of moving parts to scheduling around even 3 team members. We plan to talk through our schedules at the start of the week more, as to plan a more efficient schedule.
