`zzz
## Topic: SQL Injection

### Lab 1: SQL Injection Vulnerability in WHERE Clause Allowing Retrieval of Hidden Data

**Reflection**  
From this lab, I learned how a simple SQL injection in a WHERE clause can expose hidden data by manipulating query logic. It helped me understand how user input is directly combined into SQL queries and why that is dangerous. The most challenging part was figuring out the correct payload syntax, especially handling quotes and comments without causing server errors. This lab improved my confidence in identifying injection points and thinking logically about how backend queries work.

---

### Lab 2: SQL Injection Vulnerability Allowing Login Bypass

**Reflection**  
From this lab, I learned how SQL injection can be used to bypass authentication by manipulating the logic of a login query. It showed me how commenting out part of an SQL statement can completely ignore password checks and grant unauthorized access. The most challenging part was understanding why a small input like a single quote and a comment operator could break the entire security mechanism. This lab made the importance of secure query handling very clear to me.

---

## Topic: Authentication

### Lab 1: Username Enumeration via Different Responses

**Reflection**  
From this lab, I learned how small differences in authentication error messages can lead to username enumeration and eventually full account compromise. By carefully comparing responses, I was able to identify a valid username and then determine the correct password. The most challenging part was paying close attention to subtle wording changes in the error messages, which are easy to overlook. This lab highlighted how even minor information disclosure in login systems can have serious security consequences.

---

### Lab 2: 2FA Simple Bypass

**Reflection**  
From this lab, I learned that implementing 2FA alone is not enough if it is not properly enforced on the server side. I saw how an authentication flow can be bypassed simply by directly accessing a protected endpoint without completing the 2FA step. The most challenging part was realizing that no technical attack was needed, only an understanding of the login logic. This lab highlighted how small logical flaws can completely break authentication security.




## Booking System – Phase 1

- Set up the Booking System locally using Docker Compose.
- Verified application access and registration functionality.
- Performed manual penetration testing on the registration page.
- Identified validation and access control issues.
- Ran automated security scanning using OWASP ZAP.
- 
