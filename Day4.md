# Day 4 — Agent Frameworks, Tools & Pipelines

Course notes: agent framework comparison, resources vs. tools, Gradio chatbot, and multi-LLM evaluation pipeline.

---

## Comparing Agent Frameworks: Simplicity vs. Power

Agentic AI frameworks provide abstraction and glue code for interacting with LLMs, so development can focus on business problems rather than low-level details.

| Approach | Notes |
|----------|--------|
| **No framework** | Connect directly to LLMs via APIs. Maximum control; can be cumbersome for complex applications. |
| **OpenAI Agents SDK** | Lightweight and flexible; supports rapid development with optional guardrails. |
| **CrewAI** | Low-code; defines a "crew" of agents for task execution with minimal code. User-friendly, balances ease of use and functionality. |
| **Langraph** | More complex; powerful orchestration for sophisticated LLM workflows. Requires more expertise. |
| **Microsoft Autogen** | Offers various functionalities for building agents; can be more experimental than the others. |

---

## Resources vs. Tools

- **Resources** provide foundational knowledge; **tools** are practical applications that extend LLM capabilities. The distinction matters for effective AI development.
- Tools (e.g., Pushover for notifications) are introduced with setup and usage; the course demonstrates simplicity compared to heavier services.
- Functions to record user interactions allow the LLM to adapt to user questions and interests, with optional immediate feedback (e.g., notifications).
- **Technical implementation:** JSON is used to define functions and parameters for communication between the LLM and tools. Code cells must be run in the correct order to avoid errors.

---

## Web Chatbot with Gradio & OpenAI

- **Gradio** is a user-friendly interface for building applications with ML models and LLMs.
- Setup covers creating a chat interface where users select an AI model (e.g., OpenAI's Chat model) to power the chatbot.
- An AI agent is created to process user messages and generate responses; chat models are integrated into the Gradio interface.

---

## Using Gemini to Evaluate GPT-4: Multi-LLM Pipeline

- **Process:** Send a question to GPT-4, retrieve the answer, then use Gemini to evaluate the quality of that response.
- **Function calls:** A query is sent to GPT-4 (e.g., "Do you hold a patent?"); the response is captured and passed to an evaluation function.
- **Gemini evaluation:** The evaluation function creates an evaluator object with Gemini. The evaluator judges whether the response is acceptable (e.g., relevance, comprehensiveness).
- **Feedback:** Evaluation returns whether the response is acceptable and whether it invites further discussion, giving quick insight into model output quality.
- **Structured outputs:** Gemini can return structured outputs (e.g., JSON) by specifying the desired response shape for easier handling in applications.
