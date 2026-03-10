# GDPR Compliance Checklist – Web-based Booking System

| **Result** | **Personal data mapping and minimization** |
| :----: | :--- |
| &nbsp;⚠️&nbsp; | Have all personal data collected and processed in the system been<br> identified? (email, birthdate, role are visible in registration but not documented anywhere) |
| &nbsp;⚠️&nbsp; | Have you ensured that only necessary personal data is collected (data minimization)? (birthdate may not be strictly required for a booking system) |
| &nbsp;✅&nbsp; | Is user age recorded to verify that the booker is over 15 years old? (birthdate is collected during registration) |

---

| **Result** | **User registration and management** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Does the registration form (page) include GDPR-compliant consent for processing<br> personal data (e.g., acceptance of the privacy policy)? (terms of service acceptance checkbox)|
| &nbsp;❌&nbsp; | Can users view, edit, and delete their own personal data via their account? (no delete function available) |
| &nbsp;❌&nbsp; | Is there a mechanism for the administrator to delete a reserver in<br> accordance with the "right to be forgotten"? (not visible in UI, unclear) |
| &nbsp;✅&nbsp; | Is underage registration (under 15 years) and booking functionality restricted? (yes restricted) |

---

| **Result** | **Booking visibility** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Are bookings visible to non-logged-in users only at the resource level<br> (without any personal data)? (yes visible) |
| &nbsp;✅&nbsp; | Is it ensured that names, emails, or other personal data of bookers are not exposed<br> publicly or to unauthorized users? (yes not visible)|

--- 

| **Result** | **Access control and authorization** |
| :----: | :--- |
| &nbsp;❌&nbsp; | Have you ensured that only administrators can add, modify, and delete<br> resources and bookings? (any authorized user can create resources and modify) |
| &nbsp;✅&nbsp; | Is the system using role-based access control (e.g., reserver vs. administrator)? (yes role present in registration form) |
| &nbsp;⚠️&nbsp; | Are administrator privileges limited to ensure GDPR compliance (e.g., administrators<br> cannot use data for unauthorized purposes)? (no documentation available) |

---

| **Result** | **Privacy by Design Principles** |
| :----: | :--- |
| &nbsp;⚠️&nbsp; | Has Privacy by Default been implemented (e.g., collecting the minimum data by default)? (system collects several fields without explanation) |
| &nbsp;⚠️&nbsp; | Are logs implemented without unnecessarily storing personal data? (logging behavior not visible) |
| &nbsp;⚠️&nbsp; | Are forms and system components designed with data protection in mind<br> (e.g., secured login, minimal fields)? (basic authentication exists but no privacy documentation) |

---

| **Result** | **Data security** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Are CSRF, XSS, and SQL injection protections implemented? (most likely implemented based on the visible behavior in the ui) |
| &nbsp;✅&nbsp; | Are passwords securely hashed using a strong algorithm (e.g., bcrypt, Argon2)? (secured with md5) |
| &nbsp;⚠&nbsp; | Are data backup and recovery processes GDPR-compliant? (unclear) |
| &nbsp;✅/❌/⚠️&nbsp; | Is personal data stored in data centers located within the EU? (unclear) |

---

| **Result** | **Data anonymization and pseudonymization** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Is personal data anonymized where possible? (yes not visible for guests) |
| &nbsp;❌&nbsp; | Are pseudonymization techniques used to protect data while maintaining its utility? (no evidence of pseudonymization) |

---

| **Result** | **Data subject rights** |
| :----: | :--- |
| &nbsp;❌&nbsp; | Can users download or request all personal data related to them (data access request)? (no they can't download) |
| &nbsp;❌&nbsp; | Is there an interface or process for users to request the deletion of their personal data? (no there is no interface)|
| &nbsp;❌&nbsp; | Can users withdraw their consent for data processing? (no such options) |

---

| **Result** | **Documentation and communication** |
| :----: | :--- |
| &nbsp;❌&nbsp; | Is there a privacy policy available to users during registration and easily accessible? (nothing such available) |
| &nbsp;❌&nbsp; | Are administrators and developers provided with documented data protection practices <br>and processing activities? (nothing such provided) |
| &nbsp;❌&nbsp; | Is there a documented data breach response process (e.g., how to notify authorities <br>and users of a breach)? (nothing such implemented) |

---

**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)