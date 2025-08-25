# One-Shot Prompt Example

## Prompt
You are a QA Engineer testing the Appointment Booking module of a healthcare site.  
Functionality: Users should be able to book, reschedule, and cancel appointments.  
Constraints: Appointment slot should not be double-booked, patient must be logged in, only future dates should be allowed.  
Format: Provide test cases in a table with columns: Test Case ID, Title, Steps, Expected Result, Priority.  
Prioritization: Critical flows (booking, cancellation) → High, Rescheduling → Medium, Negative scenarios → High.  

**Example (One-Shot):**

| Test Case ID   | Title                         | Steps                                                                 | Expected Result                                    | Priority |
|----------------|-------------------------------|----------------------------------------------------------------------|---------------------------------------------------|----------|
| TC-LOGIN-01    | Valid Login with credentials  | 1. Open site <br> 2. Enter valid username/password <br> 3. Click Login | User successfully logs in and lands on dashboard | High     |

---

## AI-Generated Output

| Test Case ID   | Title                                | Steps                                                                 | Expected Result                                              | Priority |
|----------------|--------------------------------------|----------------------------------------------------------------------|-------------------------------------------------------------|----------|
| TC-BOOK-01     | Book appointment with valid details  | 1. Login as patient <br> 2. Navigate to appointments <br> 3. Select future date & slot <br> 4. Confirm booking | Appointment is successfully booked, confirmation shown      | High     |
| TC-BOOK-02     | Prevent double booking               | 1. Login <br> 2. Try booking same slot already taken <br> 3. Submit  | Error message “Slot unavailable”, booking prevented         | High     |
| TC-BOOK-03     | Booking without login                | 1. Open site <br> 2. Try booking directly without login              | Redirected to login page

