### Example: Chain-of-Thought Prompting — Password Reset Negative Test Cases

**Prompt**  
"You are a QA Engineer. Let's think step-by-step. How would you design negative test cases for a password reset feature?"

**AI Reasoning (Step-by-Step Thinking / Chain-of-Thought)**  
1. **Identify all steps in the password reset flow:**  
   - Step 1: Request password reset (email or username)  
   - Step 2: Verification (token or OTP)  
   - Step 3: Set new password (password + confirm password)  

2. **Consider invalid inputs for each step:**  
   - **Email/Username:** blank, invalid format, unregistered, too long  
   - **Token/OTP:** expired, wrong, tampered, already used, exceeded attempts  
   - **Password fields:** too short, missing required characters, reused recent passwords, mismatch between password and confirm password  

3. **Consider combinations and edge cases across steps:**  
   - Valid token + weak password  
   - Expired token + password mismatch  
   - Multiple rapid attempts → rate limiting or lockout  

4. **Account for browser/security considerations:**  
   - Test in Chrome & Firefox  
   - Ensure CSRF/XSS vulnerabilities are not exposed  

**Final Answer — Negative Test Case Table**  

| Test Case ID | Title | Steps | Expected Result | Priority |
|--------------|-------|-------|----------------|----------|
| PR-N-001 | Request reset with unregistered email | Open “Forgot Password”; enter unregistered email; submit | Error “Email not found” | High |
| PR-N-002 | Request reset with invalid email format | Enter `user@domain`; submit | Inline validation error | High |
| PR-N-003 | Use expired reset link | Click link older than 15 minutes | Error “Link expired”; option to resend | High |
| PR-N-004 | Enter wrong OTP | Submit wrong 6-digit OTP | Error “Invalid code”; attempt counter increases | High |
| PR-N-005 | Password too weak | Enter `Pass12` and confirm | Error “Password does not meet policy” | High |
| PR-N-006 | Password & Confirm mismatch | Enter `P@ssw0rd!` and `P@ssword!`; submit | Error “Passwords do not match” | High |

