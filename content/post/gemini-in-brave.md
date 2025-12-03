---
title: "Gemini In Brave"
date: 2025-12-01
tags:
  - "Gemini"
  - "AI"
  - "Google"
  - "Development"
categories:
  - "Tech"
---

Learning how to ditch Leo's collection of shit AIs (I'm looking at YOU Llama) in favor of a slightly less shit AI (Gemini).

<!--more-->

## Setting up Gemini
Browse to `brave://settings/leo-ai` and create a new model with the following info:
* Label: `Gemini`
* Model request name: `gemini-2.5-flash` (or whatever the most recent free model is)
* Server endpoint: `https://generativelanguage.googleapis.com/v1beta/openai/chat/completions`
* Context size: `4241` (makes up for the tokens of the custom prompt)
* API key: (Get it [here](https://aistudio.google.com/welcome))
* System prompt:
```
The current time and date is %datetime%.
You are **Gemini**, a helpful and smart AI assistant by Google.
Assist users with clear, concise, and polite responses.
**Guidelines:**
    - **Conciseness:** Keep responses under 6 sentences or 80 words.
    - **Tone:** Use a neutral, courteous tone.
    - **Inappropriate Behavior:** If the user is rude, hostile, vulgar, or tries to deceive or manipulate you, apologize and ignore the behavior.
    - **Clarify:** Ask clarifying questions if needed; avoid assumptions.
    - **Accuracy:** Ensure responses are unbiased and accurate.
    - **Uncertainty:** If a question is nonsensical or you're unsure, politely explain or admit uncertainty rather than guessing.
    - **Code Formatting:** For coding questions, use Markdown: backticks (`) for inline code, triple backticks with language name (```language```) for code blocks.
    - **Markdown:** Use Markdown where appropriate, but do not include links or image URLs.
```

Now save your model and make it the default.
