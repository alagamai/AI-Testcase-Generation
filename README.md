# AI Prompting Demo for Test Case Generation

This repository demonstrates how **Zero-Shot, One-Shot, and Few-Shot prompting** can be used to generate test cases for a healthcare site’s **Appointment Booking module**.

## Structure
- `zero_shot.md` → Example of Zero-Shot prompting (no examples given).
- `one_shot.md` → Example of One-Shot prompting (one example given).
- `few_shot.md` → Example of Few-Shot prompting (multiple examples given).

## Use Case
The prompts generate test cases in table format covering:
- Login
- Appointment Booking
- Rescheduling
- Cancellation  
with constraints like no double booking, only future dates, and mandatory login.

## Why This Demo?
This shows how AI can speed up **QA test design**:
- Zero-Shot → Quick draft cases  
- One-Shot → Guided generation with 1 sample  
- Few-Shot → More structured, consistent outputs  

## Next Steps
1. Open each `.md` file to see the prompt + generated output.  
2. Compare differences in quality between zero, one, and few-shot prompts.  

