# AI-Testcase-Generation

Applying the **3Cs (Context, Clarity, Constraints)** with **Role, Functionality, Constraints, Format & Prioritization**.  
Zero-Shot prompting provides no examples, while One-Shot and Few-Shot build on top of it to improve structure and consistency.

---

## Prompting Styles at a Glance

| Style              | Description | Example Usage |
|--------------------|-------------|---------------|
| **Zero-Shot**      | No examples provided. AI generates test cases directly from instructions. | "Generate test cases for appointment booking with constraints." |
| **One-Shot**       | One example given to guide AI output. | Provide 1 sample test case, then ask AI to continue. |
| **Few-Shot**       | Multiple examples for different scenarios/features. | Show booking + double-booking examples, then ask AI to extend. |
| **Chain-of-Thought** | AI explains reasoning step-by-step before giving final structured test cases. | Useful for complex flows (e.g., conflict resolution in scheduling). |

---


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

