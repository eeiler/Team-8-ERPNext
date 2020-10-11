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
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Assurance%20Cases/UAC%20case.png)  
### Evidence
## Claim 3
### ERPNext provides file change management
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Assurance%20Cases/change%20management%20case.png)  
### Evidence
## Claim 4
### ERPNext sufficiently negates malicious packet sniffing software usage
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Assurance%20Cases/Assurance%20Case%20-%20Packet%20Sniffing.PNG)  
### Evidence
# Part 2
### Assess the alignment of the evidence you identified in your diagrams, with that available (or can be made available) from the OSS project. Highlight the gaps.
### Teamwork
[Team Project Board](https://github.com/eeiler/Team-8-ERPNext/projects/3)
### Include a reflection of your teamwork for this assignment. What issues occurred? How did you resolve them? What did you plan to change moving forward? 
