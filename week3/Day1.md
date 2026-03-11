# Week 3, Day 1 — Crew AI & LightLLM

My learning notes from Day 1 of Week 3 (Agentic AI course): Crew AI platform, framework concepts, agents/tasks/processing modes, and integration with LightLLM.

---

## Main Components

| Component | What it is |
|-----------|------------|
| **Crew AI Enterprise** | Platform for deploying and managing AI agents. |
| **Crew AI UI Studio** | Low-code/no-code tool for building interactions with AI agents. |
| **Crew AI Framework** | Open-source foundation — main focus of the course. |
| **Monetization** | Understanding how Crew AI balances open-source success with commercial viability. |

---

## Approaches Within Crew AI

| Approach | Use case |
|----------|----------|
| **Crew** | Autonomous solutions; teams of agents work together. Best for creative tasks and exploratory collaboration. |
| **Flows** | Structured workflows with clear steps and decision points. Ideal for deterministic outcomes and audit trails. |

---

## Agents, Tasks, and Processing Modes

### Agents

Agents are the smallest unit of work. Each agent has:

| Attribute | Purpose |
|-----------|---------|
| **Role** | What the agent is responsible for. |
| **Goal** | The objective the agent aims to achieve. |
| **Backstory** | Background that informs the agent's behavior. |
| **Memory** | Information stored for future reference. |
| **Tools** | Resources available to the agent. |

### Tasks

Tasks are specific assignments given to agents:

| Attribute | Purpose |
|-----------|---------|
| **Description** | What the task entails. |
| **Expected Output** | What successful completion should yield. |
| **Linked to agent** | Each task gives structured work to agents. |

**Crew formation:** A crew is formed by combining multiple agents and tasks for collaborative work.

### Processing Modes

| Mode | Behavior |
|------|----------|
| **Sequential** | Tasks run one after another. |
| **Hierarchical** | A manager LLM assigns tasks to different agents. |

**Framework structure:** The Crew framework requires defined roles, goals, and backstories for agents. This improves prompting but can limit flexibility.

---

## Configuration & Code Structure

- **Configuration files:** Agents and tasks can be defined in separate **YAML** config files for clearer, more readable code.
- **Decorators:** Used to streamline creating agents and tasks and keep the codebase clean and user-friendly.

---

## Crew AI & LightLLM Integration

- **Crew AI Framework** provides abstraction so I can focus on business logic instead of low-level LLM calls.
- **LightLLM** works with Crew AI to integrate and manage **multiple LLMs** in one setup.
- **Benefits:** Simpler orchestration across LLMs and better adaptability to project needs.
- **Complexity:** Frameworks range from “no framework, direct API” to full orchestration tools; choosing depends on the problem.
- **Practice:** Picking the right LLM per task and experimenting in real setups leads to better outcomes.

---

## Tools & Environment

- **Cursor** — development environment.
- **UV** — simplifies creating virtual environments for running LLM projects.
