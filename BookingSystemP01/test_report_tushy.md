# Booking System – Phase 1 Manual Penetration Test Report

## Tester Information
- Name: Tushy Ahmed
- Course: Cybersecurity and Data Privacy
- Assignment: Booking System – Phase 1
- Testing Type: Manual Black-Box Testing

---

## Scope of Testing
The scope of this penetration test was limited strictly to the **registration functionality** of the Booking System application.  
No other pages, endpoints, or system components were tested.

---

## Test Environment
- Application: Booking System (Phase 1 – Part 1)
- Deployment Method: Docker Compose
- Operating System: Pop!_OS (Linux)
- Browser: Mozilla Firefox
- Testing Methodology: Manual black-box testing

---

## Test Case 1: Missing Input Validation Feedback

### Description
The registration form does not provide any user feedback when required fields are left empty or invalid data is entered.

### Steps to Reproduce
1. Open the registration page.
2. Submit the form without filling in any fields.

### Expected Result
The system should display clear validation error messages indicating missing or invalid input.

### Actual Result
The form submission does nothing and no error or validation message is displayed.

### Impact
Lack of validation feedback reduces usability and may conceal backend validation weaknesses from users and administrators.

### Severity
Low

---

## Test Case 2: Invalid Email Input Without Feedback

### Description
The application prevents submission when an invalid email format is entered but provides no error message to the user.

### Steps to Reproduce
1. Open the registration page.
2. Enter `abc` as the email address.
3. Fill other fields with valid data.
4. Submit the form.

### Expected Result
The system should reject the invalid email and display an appropriate error message.

### Actual Result
The form does not submit and no feedback or error message is shown.

### Impact
Users are not informed why the submission failed, leading to confusion and poor error handling.

### Severity
Low

---

## Test Case 3: Weak Password Policy Enforcement

### Description
The application allows users to register using extremely weak passwords.

### Steps to Reproduce
1. Enter a valid email address.
2. Enter the password `123`.
3. Fill other required fields with valid data.
4. Submit the registration form.

### Expected Result
The system should enforce minimum password complexity requirements.

### Actual Result
The registration succeeds using a very weak password.

### Impact
Weak passwords significantly increase the risk of unauthorized account access.

### Severity
Medium

---

## Test Case 4: Missing Input Length Restriction for Password

### Description
The registration form does not enforce reasonable length limits on password input.

### Steps to Reproduce
1. Enter a valid email address.
2. Enter a password longer than 200 characters.
3. Submit the registration form.

### Expected Result
The system should reject excessively long password inputs.

### Actual Result
The registration succeeds with a password exceeding 200 characters.

### Impact
Lack of length restrictions may lead to performance issues or potential denial-of-service risks.

### Severity
Medium

---

## Test Case 5: Case-Sensitive Email Uniqueness Validation

### Description
Email uniqueness checks are case-sensitive, allowing multiple accounts to be created for the same email address using different letter casing.

### Steps to Reproduce
1. Register an account using `Test@mail.com`.
2. Register another account using `test@mail.com`.

### Expected Result
The system should treat email addresses as case-insensitive and reject duplicate registrations.

### Actual Result
Both registrations are accepted successfully.

### Impact
This flaw allows duplicate accounts for the same email address, which may be abused for privilege escalation or account misuse.

### Severity
Medium

---

## Test Case 6: Unrestricted Administrator Role Assignment

### Description
The registration form allows any user to self-register with the administrator role without authorization checks.

### Steps to Reproduce
1. Open the registration page.
2. Select role `administrator`.
3. Enter valid email, password, and date.
4. Submit the form.

### Expected Result
Administrator role assignment should be restricted to authorized users or require approval by an existing administrator.

### Actual Result
The registration succeeds with administrator privileges without any restriction.

### Impact
This vulnerability enables privilege escalation and could lead to full compromise of the application.

### Severity
High

---

## Summary
Manual penetration testing of the Booking System registration functionality revealed multiple security weaknesses.  
The most critical issue identified was unrestricted administrator role assignment, which enables privilege escalation.  
Additional findings included weak password enforcement, improper input validation feedback, and flawed email uniqueness handling.  
These issues should be addressed to improve the security and reliability of the system.

