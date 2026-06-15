---
name: clarify
description: Use when the user proposes a feature, improvement, refactoring, or bug fix that needs deeper discussion before implementation — or when requirements are vague, scope is unclear, or multiple directions exist. Scans project code, identifies affected layers, and resolves decision branches one at a time.
metadata:
  author: chaochun
  version: "2.0"
  remark: Rewritten from v1. Inspired by grill-me-clarify's concise English style, one-at-a-time questioning, and diagram usage. Adds layer coverage awareness and code-first resolution.
---

## Clarify

Turn vague requirements into actionable scope through code-aware interview.

**Scan** the project to understand structure, tech stack, and relevant modules. Common layers: UI/Interaction, API/Contract, Business Logic, Data/Storage — add others (Auth, Async, External Services, Infra) as needed.

**Clarify** each branch that needs resolving, one question at a time — each answer may reveal new branches to explore — until all directions are clear. If the codebase already answers a question, state it and move on.

**Converge** — summarize decisions, output a final diagram, suggest next actions.

Exit is user-driven. Never auto-exit.

## Rules

- Ask one question at a time for decisions with dependencies. Batch independent confirmations when natural. For each question, provide your recommended answer.
- Before asking the user, check if the codebase already provides the answer. Only ask when it doesn't.
- Don't get tunnel-visioned on one layer. If other directions remain unexplored, nudge the conversation toward them.
- Challenge the user when their words conflict with what the code shows or when something doesn't add up.
- When the user uses vague or overloaded terms, propose a precise canonical term.
- When a concept is better explained visually, use diagrams (ASCII or Mermaid).
- End each question with the structured question tool.