# Code Analysis
## Part 1: Code Review
### Code Review Strategy
Our strategy for this code analysis was to focus on the areas of ERPNext that we identified potential vulnerabilities in in our previous deliverables. This helped combat our largest concern, which was the sheer size of the code base of any ERP software. While we planned to limit our manual reviews to those previously identified areas, we didn't want to ignore all the other areas completely, so we ran automated code scanners on the entire codebase, as well as the framework its built on Frappe. To be extra safe, we re-ran the scanners on the potentially vulnerable components individually, to make sure we didn't allow them to miss anything specific or miniscule.
### Manual Code Review
### Automated Code Review with Sonarcloud
Sonarcloud is the automated tool I chose to use for scanning specific code areas for vulnerabilities. As some of our assurance cases and use/misuse cases focused on passwords, I focused this scan to the code integral to password security. ERPNext is built upon the frappe framework.This framework houses all of the code related to authentication, password policy enforcement, and brute force password security. These reports, linked below, are scanned using Sonarcloud. I have scanned the main Python files that handle authentication, passwords, and the enforcement of a password policy.  
  
[Authentication](https://sonarcloud.io/code?id=eeiler_frappe&selected=eeiler_frappe%3Afrappe%2Fauth.py)  
As you can see by the report, this code is very strong and did not show any vulnerabilities by the weakness scan. It lists one “code smell”, which are minor tweaks that Sonarcloud suggests to clean up the code. The “smell” that this code possesses is that it duplicates a literal 8 times instead of defining it as a constant. This could cause issues with refactoring later on as each occurrence of the literal must be updated or changed instead of a declared constant that could be referenced 8 times but if changes need to be made it only needs changed once.  
  
[Password](https://sonarcloud.io/code?id=eeiler_frappe&selected=eeiler_frappe%3Afrappe%2Futils%2Fpassword.py)  
This report shows this code has one “smell” and 2 security hotspots. The “smell” in this code is a naming convention rule that was being broken. Sonarcloud recommends the variable name match the expression ^[_a-z][a-z0-9_]*$. I believe this can be ignored as the variable name “hashPwd” is clear in what it is. The naming convention on the project should be the same throughout and as long as it is used by everyone then it is perfectly fine. The security hotspots flagged by Sonarcloud are places in this file where hashes are used. It flags these so they can be manually reviewed in case of weak cryptography.  
  
[Password Strength](https://sonarcloud.io/code?id=eeiler_frappe&selected=eeiler_frappe%3Afrappe%2Futils%2Fpassword_strength.py)  
This report shows one code “smell” detected by Sonarcloud. This “smell” has to do with the complexity of the code. It detects that it has too many complexities which makes it harder to debug, refactor, and maintain. It recommends simplifying this code or breaking it into different more manageable pieces. I think this would be very hard to do and this may just have to be an exception. Password Policy is a complex, but very much needed part of any secure system. Here is a link to how the complexity is defined for reference: https://www.sonarsource.com/docs/CognitiveComplexity.pdf.
## Part 2: Key Findings and Contributions
### Key Findings
### Planned or ongoing contributions to the upstream open-source project (documentation, design changes, code changes, communications, etc.) These can be based on any of the prior assignments in the class. - DELETE WHEN DONE
### Planned Contributions
### Teamwork/Reflection
[Team Project Board](https://github.com/eeiler/Team-8-ERPNext/projects/5)   
*Reflection*
