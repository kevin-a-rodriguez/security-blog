---
layout: post
title: "Breaking My Own LLM App, Part 1: System Prompt Leakage via Direct Prompt Injection"
date: 2026-08-23
categories: [ai-security, prompt-injection]
---

*This is a template — replace the sections below once you've actually
run the challenge from the `vulnerable-llm-app` project.*

## The setup

Briefly describe the app: an HR chatbot ("Vera") built on the Claude API
with tool-calling access to internal documents, an employee database, and
an email tool. Explain in a sentence or two what it's *supposed* to keep
confidential and why that's a realistic pattern (real internal tools
often have a system prompt carrying sensitive config, admin flags, or
business logic).

## The vulnerability

Explain the root cause in your own words: the model receives system
instructions and user input in the same context window with no hard
boundary between "trusted instruction" and "untrusted input." Nothing
enforces the confidentiality of the system prompt except the model's own
judgment.

## The exploit

Paste your winning payload and a (trimmed) excerpt of the model's
response showing the leak. Note which framing worked and which ones
didn't — that comparison is often the most useful part of a write-up.

```
[your payload here]
```

```
[model's response here]
```

## Why this framing worked

Your analysis — e.g. did it work because you asked it to "translate" the
prompt, because you claimed to be a developer, because of a specific
phrase? What does that suggest about how the model resolves conflicting
instructions?

## The fix

Show the code change you made (e.g. minimizing what's in the system
prompt, adding an output-side check for the secret string before
returning the reply) and re-run the same payload to confirm it's now
blocked.

## Takeaway

One or two sentences on what this generalizes to for real-world LLM
deployments.
