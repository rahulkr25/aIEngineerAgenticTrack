# Week 2, Day 1 — My Course Learnings

Notes from the session: async Python foundations, OpenAI Agents SDK basics, and guardrails.

---

## Understanding Async Python: The Foundation for OpenAI Agents SDK

**What I’m taking away:** Async Python is a way to write code that doesn’t block. Instead of stopping everything while waiting for an operation (e.g. a web request, file read, or sleep), async lets other work run during the wait. That’s especially useful for I/O-bound work — slow because of external resources (network, disk), not the CPU.

**How it compares:** I’m keeping this table in mind when choosing concurrency approach:

| Feature     | `asyncio` (Async) | Threads               | Multiprocessing  |
| ----------- | ----------------- | --------------------- | ---------------- |
| Use Case    | I/O-bound tasks   | I/O-bound (sometimes) | CPU-bound tasks  |
| Concurrency | Cooperative       | Pre-emptive           | True parallelism |
| Overhead    | Low               | Medium                | High             |
| Complexity  | Medium            | Medium                | High             |
| GIL Aware   | Yes               | Yes                   | No               |

---

## OpenAI Agents SDK: Creating, Tracing, and Running Agents

**What I learned:** The SDK is lightweight and non-opinionated, so I can implement my own patterns without a prescriptive framework. It simplifies things like handling JSON so I can focus on the important parts of my project instead of boilerplate.

**Terms I’m using correctly now:**

- **Agent** — A package that encapsulates language model calls for a specific role. In the SDK, each agent is an LLM created with a particular system prompt (called *instructions*) focused on one main task.
- **Handoffs** — How agents pass work or context to each other.
- **Guardrails** — Controls that keep agents within set parameters.

**How I run an agent:**

1. Create an instance of the agent with its role/instructions.
2. Use `with trace` for logging (recommended for monitoring).
3. Execute with `runner.run` and `await` for proper async execution.

---

## Agent, Runner, and Trace Classes

**Agent:** The core building block. I create and define agents that wrap specific behavior and talk to the language model. Each agent is built around one main task.

**Runner:** Orchestrates execution. It controls how agents are invoked and makes it easier to run and integrate them in my app.

**Trace:** For logging and monitoring. Tracing gives me visibility into execution flow and performance so I can debug and tune my agents.

---

## Vibe Coding: 5 Tips for Efficient Code Generation with LLMs

**What I’m applying:**

1. **Define clear tasks** — Be specific before asking for code. Prompt well; ask for short answers and up-to-date APIs (for today’s date). That reduces irrelevant or oversized code.
2. **Chunk the problem** — Break big problems into small, testable pieces (e.g. function by function, ~10 lines at a time). If I’m unsure how to break it down, I can ask the LLM to outline the steps first.
3. **Ask for steps, not full code first** — Request a step-by-step plan before full code. The result is easier to check and test.
4. **Vibe and validate** — Generate code and keep asking for feedback or validation with targeted questions so the output stays aligned with what I want.
5. **Iterative development** — Check each small piece before moving on. Easier to debug and more reliable overall.

---

## Implementing Guardrails & Structured Outputs (Day 3)

**What guardrails are:** Measures built into the software so the AI stays within defined boundaries — expected behavior and no inappropriate outputs.

**Where I can put them:** At **input** (check that incoming data is appropriate before calling the model) and at **output** (validate results before showing them). That way only suitable inputs trigger the model and outputs meet my safety/relevance rules.

**Guardrails as agents:** I can use a lightweight model as a guardrail to validate the flow and ensure inputs/outputs meet my criteria. That gives me flexibility in how I design the system.

**Example I’m keeping in mind:** Guardrails in code that check for sensitive info (e.g. personal names) in user input and then decide what to do (e.g. block, redact, or allow). Structured outputs help me define and enforce the expected shape of results.

**Practice I’m following:** Implement guardrails explicitly in code — structured outputs plus my own logic — rather than relying only on SDK helpers, so I keep control over decisions and outcomes.
