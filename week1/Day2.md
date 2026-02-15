# Day 2 — LLM Workflow & Agent Design Patterns

Course notes: five workflow design patterns and agent vs. workflow distinctions.

---

## Workflow Design Patterns

Five patterns for structuring effective LLM workflows:

| Pattern | Description |
|--------|-------------|
| **Prompt Chaining** | Sequence LLM calls so the output of one model becomes the input of the next. Enables precise task framing, clearer responses, and structured pipelines. |
| **Routing** | One LLM decides which specialized model handles each task. Keeps concerns separated and lets each model play to its strengths. |
| **Parallelization** | Split work into smaller pieces that run at the same time. Orchestration code runs different tasks or repeated tasks in parallel for speed and consistency. |
| **Orchestrator–Worker** | An LLM acts as orchestrator: it decomposes complex tasks and assigns subtasks to other LLMs. Task distribution can be dynamic and context-dependent. |
| **Evaluator–Optimizer** | One LLM produces a solution; another evaluates it. The evaluator checks correctness and gives feedback, forming an iterative loop that improves reliability and quality. |

---

## Agent vs. Workflow Patterns

| Aspect | Notes |
|--------|--------|
| **Open-ended design** | Agents are flexible and adaptive, with no fixed step order. Supports creative, exploratory problem-solving; trade-off is less predictability in task order and output quality. |
| **Feedback loops** | Agents maintain ongoing interaction with their environment and support request–response cycles for continuous improvement and adaptation. |
| **Challenges of autonomy** | Task sequences can be unpredictable and output quality can vary; design and operations must account for these when building reliable systems. |
| **Mitigation** | **Monitoring** — visibility into how models interact. **Guardrails** — boundaries and checks so behavior stays within acceptable limits. |

**Summary:** Workflows give controlled, repeatable pipelines; agents give flexibility and adaptation at the cost of predictability. Use workflows when the path is well understood; use agents when exploration and adaptation are needed.
