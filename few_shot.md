# Few-Shot Prompting – Appointment Booking Module  

## Prompt  
You are a QA Engineer testing the Appointment Booking module of a healthcare site.  
Generate test cases in a table with columns: **Test Case ID, Title, Steps, Expected Result, Priority.**  

**Functionality:** Users should be able to book, reschedule, and cancel appointments.  
**Constraints:** Appointment slot should not be double-booked, patient must be logged in, only future dates should be allowed.  
**Prioritization:** Critical flows (booking, cancellation) → High, Rescheduling → Medium, Negative scenarios → High.  

---

## Examples (Few-Shot Input)  

| Test Case ID | Title | Steps | Expected Result | Priority |
|--------------|-------|-------|----------------|----------|
| TC-BOOK-01 | Book Appointment with valid details | 1. Login as patient <br> 2. Navigate to Appointment Booking <br> 3. Select doctor, date, time <br> 4. Confirm booking | Appointment is successfully booked and confirmation message shown | High |
| TC-BOOK-02 | Prevent double-booking of same slot | 1. Patient A books appointment for Dr. X at 10 AM <br> 2. Patient B tries to book Dr. X at 10 AM <br> 3. Submit booking | System should show "Slot already booked" and prevent booking | High |

---

## AI Generated Output (Continuation)  

| Test Case ID | Title | Steps | Expected Result | Priority |
|--------------|-------|-------|----------------|----------|
| TC-BOOK-03 | Prevent booking in the past | 1. Login as patient <br> 2. Attempt to book appointment for yesterday’s date <br> 3. Submit booking | System should display error "Cannot book past dates" | High |
| TC-RES-01 | Reschedule appointment to valid future date | 1. Login as patient <br> 2. Open upcoming appointment <br> 3. Click reschedule <br> 4. Select new date/time <br> 5. Confirm | Appointment successfully rescheduled, confirmation updated | Medium |
| TC-RES-02 | Prevent rescheduling to past date | 1. Login as patient <br> 2. Open existing appointment <br> 3. Try rescheduling to yesterday’s date <br> 4. Confirm | Error "Invalid date selection" shown | High |
| TC-CANCEL-01 | Cancel existing appointment | 1. Login as patient <br> 2. Open upcoming appointment <br> 3. Click Cancel and confirm | Appointment is cancelled, user notified | High |
| TC-CANCEL-02 | Prevent cancelling already cancelled appointment | 1. Login as patient <br> 2. Cancel an appointment <br> 3. Try cancelling same appointment again | Error "Appointment already cancelled" shown | High |

---

