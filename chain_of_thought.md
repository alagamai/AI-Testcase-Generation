# Chain-of-Thought Prompting for Test Case Generation

## Prompt
Role: You are a QA Engineer testing the **Appointment Booking** module of a healthcare site.  
Functionality: Users should be able to book, reschedule, and cancel appointments.  
Constraints: Appointment slot should not be double-booked, patient must be logged in, only future dates should be allowed.  
Format: Provide test cases in a table with columns: **Test Case ID, Title, Steps, Expected Result, Priority**.  
Prioritization: Critical flows (booking, cancellation) → High, Rescheduling → Medium, Negative scenarios → High.  

**Instruction:** First, think step by step about the functionality, constraints, and possible edge cases (reasoning path). Then, generate the test cases.

---

## Expected Reasoning (Chain of Thought)
1. **Booking Flow:** Validate successful booking with valid details → High priority.  
2. **Negative Booking:** Try to book in the past or with missing login → High priority.  
3. **Double Booking:** Prevent same slot booking by multiple users → High priority.  
4. **Rescheduling:** Allow rescheduling to valid future date → Medium priority.  
5. **Cancellation:** User should be able to cancel successfully → High priority.  

---

## Expected Output

| Test Case ID     | Title                                  | Steps                                                                 | Expected Result                                              | Priority |
|------------------|----------------------------------------|----------------------------------------------------------------------|-------------------------------------------------------------|----------|
| TC-BOOK-01       | Book appointment with valid details    | 1. Login <br> 2. Go to booking <br> 3. Select valid future date/slot <br> 4. Confirm booking | Appointment is booked successfully                          | High     |
| TC-BOOK-02       | Attempt booking without login          | 1. Open booking page without login <br> 2. Select date/slot <br> 3. Try to confirm | Error: "Login required to book appointment"                 | High     |
| TC-BOOK-03       | Attempt double-booking same slot       | 1. User A books slot <br> 2. User B attempts same slot <br> 3. Confirm | Error: "Slot already booked"                                | High     |
| TC-BOOK-04       | Book appointment with past date        | 1. Login <br> 2. Select past date <br> 3. Try to confirm              | Error: "Invalid date – must select a future date"           | High     |
| TC-RESCH-01      | Reschedule valid booking               | 1. Login <br> 2. Open existing booking <br> 3. Change to future slot <br> 4. Confirm | Booking updated successfully                                | Medium   |
| TC-CANCEL-01     | Cancel existing booking                | 1. Login <br> 2. Open booking <br> 3. Click Cancel                    | Appointment is cancelled successfully                       | High     |

