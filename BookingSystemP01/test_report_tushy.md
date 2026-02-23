# 1️⃣ Introduction

**Tester(s):**
- Name: Jannatul Tushy

**Purpose:**
- Identify security vulnerabilities and weaknesses in the registration functionality of the Booking System application (Phase 1).

**Scope:**
- **Tested components:** Registration page and related backend logic (form submission, input validation, role assignment, email uniqueness)
- **Exclusions:** All other application features (login, booking, profile management, admin panel, etc.)
- **Test approach:** Manual Black-box testing

**Test environment & dates:**
- **Start:** Not specified
- **End:** Not specified
- **Test environment details (OS, runtime, DB, browsers):**  
  Pop!_OS (Linux), Docker Compose deployment, Mozilla Firefox browser

**Assumptions & constraints:**
- Testing performed strictly on the registration endpoint/functionality
- No source code access (pure black-box)
- No pre-existing accounts or special credentials required

---

# 2️⃣ Executive Summary

**Short summary (1-2 sentences):**  
Manual black-box testing of the Booking System registration functionality exposed critical security flaws — most notably the ability for anyone to self-register as an **administrator** — along with weak password controls, improper input handling, and flawed email uniqueness checks.

**Overall risk level:** High

**Top 5 immediate actions:**
1. **Immediately remove** the administrator role option from the public registration form or implement strict authorization controls
2. Enforce a **strong password policy** (minimum length 12+, complexity rules, block common/weak passwords)
3. Add **maximum length restrictions** on password and other free-text fields (e.g. 128–255 characters max)
4. Normalize emails to lowercase and enforce **case-insensitive uniqueness** during registration
5. Implement **clear client-side and server-side validation messages** for all required/invalid inputs

---

# 3️⃣ Severity scale & definitions

| **Severity Level** | **Description**                                                                                  | **Recommended Action**            |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------------------|
| 🔴 **High**        | A serious vulnerability that can lead to full system compromise or data breach (e.g., privilege escalation, RCE). | *Immediate fix required*          |
| 🟠 **Medium**      | A significant issue that may require specific conditions or user interaction (e.g., weak auth controls). | *Fix ASAP*                        |
| 🟡 **Low**         | A minor issue or configuration weakness (e.g., poor UX, missing feedback).                      | *Fix soon*                        |
| 🔵 **Info**        | No direct risk, but useful for system hardening (e.g., missing headers).                        | *Monitor and fix in maintenance*  |

---

# 4️⃣ Findings

| ID   | Severity   | Finding                                           | Description                                                                                   | Evidence / Proof                                      |
|------|------------|---------------------------------------------------|-----------------------------------------------------------------------------------------------|-------------------------------------------------------|
| F-01 | 🔴 High    | Unrestricted Administrator Role Assignment        | Any unauthenticated user can select and register with the `administrator` role               | Registration form allows selecting "administrator" role and succeeds |
| F-02 | 🟠 Medium  | Weak Password Policy Enforcement                  | Extremely weak passwords (e.g. "123") are accepted without any complexity requirements       | Registration succeeds with password "123"             |
| F-03 | 🟠 Medium  | No Input Length Restriction on Password           | Passwords longer than 200 characters are accepted                                             | Registration succeeds with >200 character password    |
| F-04 | 🟠 Medium  | Case-Sensitive Email Uniqueness Check             | Same email address with different casing (e.g. Test@mail.com vs test@mail.com) can be registered multiple times | Two accounts created successfully with same email (different case) |
| F-05 | 🟡 Low     | Missing Client-Side & Server-Side Validation Feedback | No error messages are displayed for empty fields, invalid email formats, or other failures — form simply does nothing | Form submission with empty/invalid data shows no feedback |

> [!NOTE]  
> These represent the five most important issues identified during manual testing.

---

# 5️⃣ OWASP ZAP Test Report (Attachment)


https://github.com/JannatulTusy/tusyrepo/blob/main/BookingSystemP01/zap_report_round1.md
