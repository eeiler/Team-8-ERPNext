## Case 1
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/Email%20Rec%20Case.png)  
Employees using the ERPNext software must be able to communicated through email both internally and externally.  
Email is a commonly exploited area of business for malicious attackers. The misuse case is the malicious email sender trying to spam the employee with emails that could have dangerous files inside, or be phishing for employee information.

ERPNext does use a configurable attachment limit to prevent large email sizes being used as a email DoS bomb.
ERPNext recommends for things like spam filtering, that it be done by the mail server provider external of ERPNext.
ERPNext allows for pdfs of documents to be attached to emails sent through it. Which would be received by other employees.

ERPNext is clear in the [https://docs.erpnext.com/docs/user/manual/en/setting-up/email](email section) of the user manual of certain security requirements that should be handled outside of this software, such as spam filtering, SSL, and TSL. They do provide things such as attachment limiting to prevent the DoS of the ERP system.
The security provided is little by ERPNext as the pass the responsibility to the mail server provider, but something they should add is a notifier flag in the email subject when it is received from outside the company. An option to notify of an important document on internal emails also would add good clarity to the email system
