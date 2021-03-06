# Requirements for Software Security Engineering
## Case 1
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/Email%20Rec%20Case.png)  
Employees using the ERPNext software must be able to communicate through email both internally and externally.  
Email is a commonly exploited area of business for malicious attackers. The misuse case is the malicious email sender trying to spam the employee with emails that could have dangerous files inside, or be phishing for employee information.

ERPNext does use a configurable attachment limit to prevent large email sizes being used as an email DoS bomb.
ERPNext recommends for things like spam filtering, that it be done by the mail server provider external of ERPNext.
ERPNext allows for pdfs of documents to be attached to emails sent through it. Which would be received by other employees.

ERPNext is clear in the [https://docs.erpnext.com/docs/user/manual/en/setting-up/email](email section) of the user manual of certain security requirements that should be handled outside of this software, such as spam filtering, SSL, and TSL. They do provide things such as attachment limiting to prevent the DoS of the ERP system.
The security provided is little by ERPNext as they pass the responsibility to the mail server provider, but something they should add is a notifier flag in the email subject when it is received from outside the company. An option to notify of an important document on internal emails also would add good clarity to the email system.
## Case 2
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/New%20item%20use%20case.png)  
Employees using the ERPNext software must be able to add new items to the software.
Item entry is an important vector due to its role with maintaining the latest forms of stock, and that it has a direct line to the database that is typically less guarded than search functions and bars.

The ERPNext item entry screen limits what you are able to enter into specific fields, and the ability to use other forms of input validation.
There are not any visible recommendations for the security of new item creation.

ERPNext does not provide any additional security requirements for Item entry screen or process. It is possible to create additional input validation plugins through the development module. Additional input validation should be added to protect against possible insider threats or adversaries that get access and do a SQL injection into the inbuilt MYSQL database. Denial of service for the item database is also a problem, but that is typically handled through the inbuilt systems for restart and backups. 
## Case 3
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/Encrypted%20Info.PNG)  
ERPNext approaches server side security by both encrypting data and banning suspicious or known malicious IP addresses. It does this automatically using Fail2ban and LetsEncrypt. 

Employees of organizations utilizing ERPNext can provide their financial information knowing it will be encrypted at all times and shielded from malicious IP addresses. The good thing for the organization is LetsEncrypt is free, so they don't have to account for any additional costs or fees to conduct payroll and other practices that utilize confidential information securely. 
## Case 4 
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/User%20Login.PNG)  
While modern hackers have many options when it comes to password cracking as seen in the misuse case above (i.e. Brute Force, Guesswork, Malicious Password Recovery), ERPNext takes a couple pretty standard measures to make sure their users don't fall victim to them. Both forced lockout after X attempts and forced password reset, both optional settings (https://erpnext.com/security/frappe-hosting), give organizations the power to make any of the aforementioned attacks very hard, if not impossible.

Setting up a bot to fill in random passwords until it cracks the user's account won't work if the account after a couple tries. Similarly, the hacker would have to do some impressive guesswork to get in in the same amount of tries. Granted, a hacker abusing password recovery systems has the best shot against these defenses, but common resets still make their job that much harder. These settings should deter the typical hacker.
## Open Source Software Project Documentation Security Issues
These two issues are found in the user manual documentation for ERPNext. When searching certain syntax and functions you can see that it is displayed in the search bar. This should be fixed just do not show too much coding functionality as that can lead to vulnerabilities being found. Examples are shown below: 
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/Doc%20search%20issue.png)
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Requirements%20for%20SSE/Doc%20search%20issue%202.png)  
ERPNext website function is unable natively to restrict what users are able to view the website. You cannot limit the access of the website generated by ERPNext to certain people. If you publish the website it, will be publicly visible. This is due to the fact that products are directly fetched from the Item Master records, and the future to specify visibility has not been implemented. Current item visibility is a binary system, so it either appears on the site or it doesn't.
## Teamwork
[Team Project Board](https://github.com/eeiler/Team-8-ERPNext/projects/1)  
We decided to get started early in the week on the use cases. This allowed us to use our team checkup to review how the cases should be done. We struggled to get a strong grasp on the cases at first, so we asked questions in a meeting with our professor and studied the lecture again before meeting to work on the cases again. We plan to continue starting early in the week, so we can get any questions and feedback at our checkup meetings. We also ran into scheduling issues this week. There are a lot of moving parts to scheduling around even 3 team members. We plan to talk through our schedules at the start of the week more, as to plan a more efficient schedule.
