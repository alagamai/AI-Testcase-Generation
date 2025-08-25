# Zero-Shot Prompt Example

## Prompt
Role: You are a QA Engineer testing the Appointment Booking module of a healthcare site.  
Functionality: Users should be able to book, reschedule, and cancel appointments.  
Constraints: Appointment slot should not be double-booked, patient must be logged in, only future dates should be allowed.  
Format: Provide test cases in a table with columns: Test Case ID, Title, Steps, Expected Result, Priority.  
Prioritization: Critical flows (booking, cancellation) → High, Rescheduling → Medium, Negative scenarios → High.  

---

## AI-Generated Output

| Test Case ID   | Title                                | Steps                                                                 | Expected Result                                              | Priority |
|----------------|--------------------------------------|----------------------------------------------------------------------|-------------------------------------------------------------|----------|
| TC-BOOK-01     | Book appointment with valid details  | 1. Login as patient <br> 2. Navigate to appointments <br> 3. Select future date & slot <br> 4. Confirm booking | Appointment is successfully booked, confirmation shown      | High     |
| TC-BOOK-02     | Prevent double booking               | 1. Login <br> 2. Try booking same slot already taken <br> 3. Submit  | Error message “Slot unavailable”, booking prevented         | High     |
| TC-BOOK-03     | Booking without login                | 1. Open site <br> 2. Try booking directly without login              | Redirected to login page                                    | High     |
| TC-RESCHED-01  | Reschedule to valid future date      | 1. Login <br> 2. Open existing booking <br> 3. Select new date/time  | Appointment successfully rescheduled                        | Medium   |
| TC-RESCHED-02  | Reschedule to past date (invalid)    | 1. Login <br> 2. Open existing booking <br> 3. Select past date      | Error message “Past dates not allowed”                      | High     |
| TC-CANCEL-01   | Cancel existing appointment          | 1. Login <br> 2. Navigate to booked appointment <br> 3. Click cancel | Appointment successfully cancelled, confirmation shown      | High     |
| TC-CANCEL-02   | Cancel already cancelled appointment | 1. Login <br> 2. Try to cancel an already cancelled appointment      | Error message “No active appointment found”                 | High     |

