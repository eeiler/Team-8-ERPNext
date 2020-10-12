# Assurance Cases
## Claim 1
### ERPNext protects against password cracking
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Assurance%20Cases/Assurance%20Case_%20Password%20Cracking.png)  
### Evidence
E1: ERPNext offers [configurable IP addresses](https://docs.erpnext.com/docs/user/manual/en/setting-up/users-and-permissions/adding-users#28-security-settings). This allows administrators using the software to approve only company IP addresses. This can halt outside attacks by not allowing them access to the system. IP addresses are unique so another device should not be able to use the approved address once it is in use.  

E2: The IP addresses should only be added when a new one is needed, leaving no extra IPs unused that could be exploited to gain access to the system.  

E3: Brute force or guesswork attacks would take too long to crack a password while not getting locked out as ERPNext offers [forced password resets](https://docs.erpnext.com/docs/user/manual/en/setting-up/settings/system-settings#16-password) after a configured time. Recommended time is a month, which would likely stop an attack on a strong password even without the lock out time.  

E4: ERPNext has configurable [password policy](https://docs.erpnext.com/docs/user/manual/en/setting-up/settings/system-settings#16-password) allowing the administrators to require strong passwords for all users. This will drastically reduce likelihood of brute force or guesswork attacks on the passwords of their users.  
## Claim 2
### ERPNext has acceptable amounts of UAC
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Assurance%20Cases/UAC%20case1.png)  
### Evidence
E1: ERPNext has the capacity for administrators to limit which modules given users are capable of accessing per [release notes 5](https://github.com/frappe/erpnext/wiki/Version-5-Release-Notes).

E2: ERPNext offers [user](https://docs.erpnext.com/docs/user/manual/en/setting-up/users-and-permissions/user-permissions) and [role](https://docs.erpnext.com/docs/user/manual/en/setting-up/users-and-permissions/role-based-permissions) based file permissions. This allows for Administrators to limit which user have access to which file based on who they are and which role they have.

E3: ERPnext has its Github page submitions reviewed before implementation as show by a number of denied changes. This allows the primary developers to control what gets added and what does not making sure that bad actors do not compromise the main code.
## Claim 3
### ERPNext provides file change management
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Assurance%20Cases/change%20management%20case.png)  
### Evidence
E1: ERPNext offers a document timeline that was added in [release #5](https://github.com/frappe/erpnext/wiki/Version-5-Release-Notes). This allows file owners and administrators to see what events have happend over a specific document
## Claim 4
### ERPNext sufficiently negates malicious packet sniffing software usage
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Assurance%20Cases/Assurance%20Case%20-%20Packet%20Sniffing.png)  
### Evidence
E1: Fail2ban tracks IP addresses that make frequent or abnormal requests and automatically bans them.

E2: Fail2ban is only one part of the two part protection used. Even if the IP gets packets before it gets blocked, they will be encrypted by LetsEncrypt, the latter part of the protection.

E3: LetsEncrypt keeps all plans of action for different scenarios in their Policy and Legal Repository: https://letsencrypt.org/repository/

E4: LetsEncrypt checks for websites using malware with Google's Safe Browsing API before issuing certificates.

E5: LetsEncrypt uses 4096 bit RSA encryption for their security key. The biggest key cracked by the best quantum computers today is 6 bit, so we are a long ways from decrypting 4096 bit encryption. https://www.quintessencelabs.com/blog/breaking-rsa-encryption-update-state-art/

E6: Referencing E5, even if a computer like this does come about in the next 20 years, it's unlikely it would be in the hands of a hacker using something as remidial as packet sniffing software, and our level of encryption will probably also improve by then.
# Part 2
### Teamwork
[Team Project Board](https://github.com/eeiler/Team-8-ERPNext/projects/3)
### Reflection
We ran into more challenges this week than any of the previous. First off, due to busy schedules, we were never able to meet as an entire team. We made do by keeping the communication up in the chat on our Discord channel, but it wasn't a perfect substitute for meeting in person or virtually. This is especially true when considering the second problem, that we had the least understanding about this assignment as compared to all of the previous. Moving forward, we need to do better to make sure we have a full and complete grasp on the previous week's module as a team before heading into the week of creating the deliverable. We also need to make sure to find time to meet in person at least once, preferably twice. Last but not least, one skill we developed as a team this time around was establishing that it is okay to reach out to eachother when we're stuck, rather than doing all of our work outside of meetings in silos. Keeping communication open in that way allowed us to push through the major roadblocks we ran into on this go and is something we plan to continue moving forward.
