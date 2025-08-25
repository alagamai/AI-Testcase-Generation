### Chain-of-Thought Prompt — Password Reset Negative Test Cases (Table Format)

**Prompt**  
"You are a QA Engineer. Let's think step-by-step. How would you design negative test cases table for a password reset feature?"

**Step-by-Step Thinking (Chain-of-Thought)**  
1. **Understand the flow:**  
   - Request password reset (email/username)  
   - Verification (link/token or OTP)  
   - Set new password (password + confirm password)  

2. **Identify invalid inputs per step:**  
   - Email/Username: blank, invalid format, unregistered, overly long  
   - Token/OTP: expired, wrong, tampered, reused, exceeded attempts  
   - New Password: too short, missing complexity, reused recent password, mismatch  

3. **Consider cross-step edge cases:**  
   - Valid token + weak password  
   - Expired token + password mismatch  
   - Multiple rapid attempts → rate limiting  

4. **Security & Browser Checks:**  
   - Test in Chrome & Firefox  
   - Ensure CSRF/XSS vulnerabilities are handled  

**Final Test Case Table**

| Test Case ID | Title | Steps | Expected Result | Priority |
|--------------|-------|-------|----------------|----------|
| PR-N-001 | Unregistered email | Open reset page; enter unregistered email; submit | Error “Email not found” | High |
| PR-N-002 | Blank email | Leave email blank; submit | Error “Email is required” | High |
| PR-N-003 | Invalid email format | Enter `user@domain`; submit | Inline validation error | High |
| PR-N-004 | Expired link | Click link older than 15 minutes | Error “Link expired”; option to resend | High |
| PR-N-005 | Wrong OTP | Enter wrong 6-digit OTP; submit | Error “Invalid code”; attempt counter increases | High |
| PR-N-006 | Exceed OTP attempts | Enter wrong OTP 5 times | Account temporarily locked | High |
| PR-N-007 | Weak password | Enter `Pass12` and confirm | Error “Password does not meet policy” | High |
| PR-N-008 | Reuse recent password | Enter last-used password; submit | Error “Cannot reuse recent passwords” | High |
| PR-N-009 | Password mismatch | Enter password & confirm that do not match; submit | Error “Passwords do not match” | High |
| PR-N-010 | Missing CSRF token | Submit form without CSRF token | Request rejected securely; logged | High |

