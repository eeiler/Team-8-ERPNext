# Code Analysis
## Part 1: Code Review
### Code Review Strategy
Our strategy for this code analysis was to focus on the areas of ERPNext that we identified potential vulnerabilities in in our previous deliverables. This helped combat our largest concern, which was the sheer size of the code base of any ERP software. While we planned to limit our manual reviews to those previously identified areas, we didn't want to ignore all the other areas completely, so we ran automated code scanners on the entire codebase, as well as the framework its built on Frappe. To be extra safe, we re-ran the scanners on the potentially vulnerable components individually, to make sure we didn't allow them to miss anything specific or miniscule.
### Manual Code Review
Going into our manual code review, we created the following CWE checklist so we had concise things to look for in the aforementioned potentially vulnerable areas. Keeping this checklist at the forefront of our process allowed us to move efficiently and effectively through the code base, which led to more concise results than we could've hoped for otherwise. To create the checklist, we compared potential vulnerabilities from our previous deliverables to the [most common CWE's](https://cwe.mitre.org/top25/archive/2020/2020_cwe_top25.html) in an effort to leverage lessons already learned by others in the industry and focus our efforts on the most fruitful areas we could.

#### CWE Checklist <sub><sup>(*Signifies non-applicable CWE's, reason listed following the given CWE)</sup></sub>
1.	Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')
2.	Out-of-bounds Write  
Only affects C, C++, and Assembly class.  
3.	Improper Input Validation
4.	Out-of-bounds Read*  
Only affects C and C++.  
5.	Improper Restriction of Operations within the Bounds of a Memory Buffer*  
Only affects C, C++, and Assembly class.  
6.	Improper Neutralization of Special Elements used in an SQL Command ('SQL Injection')
7.	Exposure of Sensitive Information to an Unauthorized Actor
8. Use After Free*  
Only affects C and C++.  
9.	Cross-Site Request Forgery
10.	Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection')
11.	Integer Overflow or Wraparound*  
Integer overflow is not an issue in Python as Python automatically expands variables when they grow too large for their current state.  
12.	Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal')  
13.	NULL Pointer Dereference*  
Only affects C, C++, Java, C#.
14.	Improper Authentication
15.	Unrestricted Upload of File with Dangerous Type
16.	Incorrect Permission Assignment for Critical Resource
17.	Improper Control of Generation of Code ('Code Injection')
18.	Insufficiently Protected Credentials
19.	Improper Restriction of XML External Entity Reference
20.	Use of Hard-coded Credentials
21.	Deserialization of Untrusted Data
22.	Improper Privilege Management
23.	Uncontrolled Resource Consumption
24.	Missing Authentication for Critical Function
25.	Missing Authorization

&nbsp;

[Password.py](https://github.com/frappe/frappe/blob/v12.12.0/frappe/utils/password.py)  

&nbsp;&nbsp;&nbsp;&nbsp;<sub>(CWE Reference)</sub>
* (1) Input Sanitization for XSS in Password.py is handled in another section per Pull #4560  
* (2) No Input within Password.py  
* (5) Password.py does not handle any direct interactions with SQL databases
* (6) requires additional research into thrown exceptions for Frappe, adn where paraticular varibles are shown in error logs
* (8) Does not interact with a web server directly, works though other programs for validation
* (9) Does not utilize system commands
* (11) Does not utilize Path tranversal

[Password_Strength.py](https://github.com/frappe/frappe/blob/v12.12.0/frappe/utils/password_strength.py)

* (1) Input Sanitization for XSS in Password.py is handled in another section per Pull #4560
* (2) 
* (5)
* (6)
* (8) 
* (9) 
* (11) 
* (13) 
* (14) 
* (15) 
* (16) 
* (17) 
* (18) 
* (19) 
* (20) 
* (21) 
* (22) 
* (23) 
* (24) 
* (25) 
  
### Automated Code Review with Sonarcloud
Sonarcloud is the automated tool I, Erik, chose to use for scanning specific code areas for vulnerabilities. As some of our assurance cases and use/misuse cases focused on passwords, I focused this scan to the code integral to password security. ERPNext is built upon the frappe framework.This framework houses all of the code related to authentication, password policy enforcement, and brute force password security. These reports, linked below, are scanned using Sonarcloud. I have scanned the main Python files that handle authentication, passwords, and the enforcement of a password policy.  
  
[Authentication](https://sonarcloud.io/code?id=eeiler_frappe&selected=eeiler_frappe%3Afrappe%2Fauth.py)  
As you can see by the report, this code is very strong and did not show any vulnerabilities by the weakness scan. It lists one “code smell”, which are minor tweaks that Sonarcloud suggests to clean up the code. The “smell” that this code possesses is that it duplicates a literal 8 times instead of defining it as a constant. This could cause issues with refactoring later on as each occurrence of the literal must be updated or changed instead of a declared constant that could be referenced 8 times but if changes need to be made it only needs changed once.  
  
[Password](https://sonarcloud.io/code?id=eeiler_frappe&selected=eeiler_frappe%3Afrappe%2Futils%2Fpassword.py)  
This report shows this code has one “smell” and 2 security hotspots. The “smell” in this code is a naming convention rule that was being broken. Sonarcloud recommends the variable name match the expression ^[_a-z][a-z0-9_]*$. I believe this can be ignored as the variable name “hashPwd” is clear in what it is. The naming convention on the project should be the same throughout and as long as it is used by everyone then it is perfectly fine. The security hotspots flagged by Sonarcloud are places in this file where hashes are used. It flags these so they can be manually reviewed in case of weak cryptography.  
  
[Password Strength](https://sonarcloud.io/code?id=eeiler_frappe&selected=eeiler_frappe%3Afrappe%2Futils%2Fpassword_strength.py)  
This report shows one code “smell” detected by Sonarcloud. This “smell” has to do with the complexity of the code. It detects that it has too many complexities which makes it harder to debug, refactor, and maintain. It recommends simplifying this code or breaking it into different more manageable pieces. I think this would be very hard to do and this may just have to be an exception. Password Policy is a complex, but very much needed part of any secure system. Here is a link to how the complexity is defined for reference: https://www.sonarsource.com/docs/CognitiveComplexity.pdf.  
## Part 2: Key Findings and Contributions
### Key Findings
In the summary of the Sonarcloud reports, I went through each flag that was raised. Many of these flags were nothing to be majorly concerned with, however it did mention having a cryptographer or someone qualified to ensure that the hash encrpyption is strong and is not exploitable. Frappe may already have had this done but if not it is something that should be highly considered. As for many of the minor "smells", I believe the "smell" mentioned in authentication is an easy fix so it might as well be done for future ease if there comes a time when that literal has to be changed in any way.

### Planned Contributions
We believe the rewriting of the literal as a constant in the auth.py file is a notable contribution that this team can make. It may seem like a smaller change, but many small changes can easily add up. Especially if someone is able to make a necessary change in one spot rather than eight. This contribution will be done by our team writing in the new constant and referencing the constant anywhere that the literal was being used. It will then be explained and sent in a pull request to the main codebase for approval.
  
One thing we haven't noticed during our time examining ERPNext is a type of audit log functionality. In delving deeper into this, we found numerous requests for this type of functionality dating back as far as six years (pictured below), which sparked some conversation among developers each time it was brought up. While we don't have the capacity or aptitude to implement this ourselves, we could make a request for it, with the hope being that the core team is in a better place to explore implementing an audit log than they were back then.
![](https://github.com/eeiler/Team-8-ERPNext/blob/master/Code%20Analysis/No%20Audit%20Log.PNG)

### Teamwork/Reflection
[Team Project Board](https://github.com/eeiler/Team-8-ERPNext/projects/5)   
Our teamwork has really settled into a good place this semester. We stuck to meeting the first Monday of every week when a deliverable was due, which helped us get a handle on what work we had to get done early. Moving forward with a mutual understanding of that work and our individual strengths helped us split it up as evenly as possible and attack large chunks as a team, or by breaking it up into bite size pieces. Leveraging the midweek professor meeting and usually a short follow up of our own, allowed us to dive into the harder parts of the assignment with some professionally advised direction, which we believe saved us the time of trying and failing with ill-informed strategies like we did in previous iterations. Overall, we could be a little bit more proactive as a unit, and maybe slightly better at problem solving individually, but we're satisfied with our communication, effort, and output. We all agree that we've worked on much less cohesive group projects in the past, and would be happy to work together again any time. 
