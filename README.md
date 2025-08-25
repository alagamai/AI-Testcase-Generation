# AI Prompting Demo for Test Case Generation

This repository demonstrates how **Zero-Shot, One-Shot, and Few-Shot prompting** can be used to generate test cases for a healthcare site’s **Appointment Booking module**.

## Structure
- `zero_shot.md` → Example of Zero-Shot prompting (no examples given).
- `one_shot.md` → Example of One-Shot prompting (one example given).
- `few_shot.md` → Example of Few-Shot prompting (multiple examples given).
- **chain_of_thought.md** → AI first reasons step by step (thinking process) and then generates test cases.  


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
- **Chain-of-Thought** → Step-by-step reasoning before generating test cases for better accuracy  

## Next Steps
1. Open each `.md` file (`zero_shot.md`, `one-shot.md`, `few_shot.md`, `chain_of_thought.md`) to see the prompt + generated output.  
2. Compare differences in quality between Zero-Shot, One-Shot, Few-Shot, and Chain-of-Thought prompting.  
3. Experiment by modifying prompts and observing how outputs change.  
4. Extend with more QA scenarios (e.g., Payments, Reports) to showcase broader coverage.  

