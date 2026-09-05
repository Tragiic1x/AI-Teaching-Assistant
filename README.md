# AI Teaching Assistant

An AI-powered study tool that reads uploaded lecture notes or slides (PDF, PPTX, or TXT) and lets you either ask questions about the content or generate quiz questions from it — with answers grounded strictly in what you uploaded, not the model's general knowledge.

## Tech Stack
Python, Streamlit, Groq API (Whisper/LLM), PyPDF2, python-pptx, tiktoken

## Features
- Upload notes as PDF, PPTX, or TXT
- Ask direct questions about your notes — the AI clearly says when something isn't covered, instead of guessing
- Generate custom quiz questions (multiple choice + short answer) from your uploaded content
- Token budget management to stay within API rate limits
- Basic error handling so a failed API call shows a message instead of crashing

## Setup

1. Clone this repo
2. Install dependencies:
   ```
   pip install streamlit groq tiktoken PyPDF2 python-pptx
   ```
3. Get a free API key from [Groq Console](https://console.groq.com)
4. Set it as an environment variable:
   ```
   export GROQ_API_KEY="your-key-here"
   ```
5. Run it:
   ```
   streamlit run app.py
   ```

## Notes
Notes are capped at ~4,000 tokens per upload to stay within Groq's free-tier rate limits — longer documents will be truncated rather than causing an error.
