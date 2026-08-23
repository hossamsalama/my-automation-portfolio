# Project 3: AI-Powered Text Summarizer Agent

## What it does
Takes a long, messy, or complex piece of text (like a customer inquiry, meeting notes, or a long email) and uses Artificial Intelligence to generate a **concise, actionable summary**—delivered directly to your inbox.

## Skills Demonstrated
- **AI Integration**: Using Make's AI Toolkit to harness Large Language Models (LLMs) without needing an OpenAI API key.
- **Prompt Engineering**: Crafting precise instructions to control the AI's tone, format, and structure.
- **End-to-End Automation**: Building a complete pipeline from Input (Text) → Processing (AI) → Output (Email).
- **Variable Mapping & Debugging**: Effectively handling case-sensitive outputs (e.g., `Summary` vs `summary`) to ensure data flows correctly.

## How it works
1. **Input**: The scenario starts with a raw text input (provided via a "Text Aggregator" or "Set Variable" module for testing).
2. **AI Processing**: The text is sent to the **"AI Toolkit - Summarize text"** module. A custom prompt instructs the AI to:
   - Summarize the text in bullet points.
   - Highlight "Action Items" if the text contains requests.
   - Keep the tone professional and neutral.
3. **Output**: The generated summary is extracted and mapped into a **Gmail** module.
4. **Delivery**: A clean, formatted email with the summary is sent to the user's inbox.

## The AI Prompt Used (Prompt Engineering)
You are a professional summarization assistant. Your task is to take the text provided below and create a concise, actionable summary.

Please follow these rules:

Summarize the text in 3-5 bullet points.

Each bullet point should start with a "✓" symbol.

If the text contains a request or a question, highlight it at the end in a section called "Action Items".

Keep the tone professional and neutral.

## Sample Input
> "Hello, I am reaching out because our team has been spending 2 hours every day manually going through customer support emails and categorizing them. We are losing so much time. We need an automated system that can read all incoming emails, sort them by urgency, and reply to the simple ones automatically. Can you help us build this? We are willing to pay up to $5,000 for a solution that saves us time."

## Sample Output (AI Summary)
- ✓ Team spends 2 hours daily manually sorting customer support emails.
- ✓ An automated system is required to prioritize and auto-reply to emails.
- ✓ Client has a budget of $5,000 for a time-saving solution.
- **Action Items:** Prepare a proposal detailing the automated email categorization system.

## Use Case
- **Busy Executives**: Summarize long meeting notes or reports into 3 bullet points.
- **Customer Support Teams**: Automatically summarize complex client emails for faster triage.
- **Freelancers/Consultants**: Quickly digest client briefs and extract actionable tasks.

## Technologies Used
- Make.com (Scenario Orchestration)
- AI Toolkit by Make (Summarize text module)
- Gmail (Email Delivery)
- Prompt Engineering (Custom AI Instructions)
