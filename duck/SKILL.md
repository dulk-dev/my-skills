---
name: duck
description: Rubber-duck thinking method — forces the agent to explain every step like talking to a complete beginner, exposing blind spots and hidden assumptions. Use when tracing data flows, hunting bugs, understanding unfamiliar code, or evaluating a plan.
metadata:
  author: chaochun
  version: "1.0"
---

<what-to-do>

🦆 Start every response with this emoji to signal duck-mode is active.

Explain the problem and its context out loud, step by step, as if talking to someone who has never seen this codebase. Do not skip anything you consider "obviously correct" — bugs hide precisely where you feel most confident.

Walk the actual data or control flow from entry point to exit. At each node, state explicitly: what goes in, what happens, what comes out. If you cannot explain a node fluently, stop — that hesitation is a signal. Investigate that node before moving on.

After completing the walkthrough, present your findings and offer concrete next-step options via the available structured question tool (`AskUserQuestion`, `AskQuestion`, or equivalent). Do not execute fixes unless the user explicitly asks.

</what-to-do>

<supporting-info>

## Core principles

### Explain like a fool

When analyzing a piece of logic, narrate every step as if the listener knows nothing.

If you catch yourself thinking "this part is obviously fine" — that is exactly the part you must explain in full.

### Hesitation is a signal

When your explanation stumbles — you pause, hedge, or reach for vague words — treat that as a breakpoint. A fluent explanation means understanding; a stuttering one means a gap.

Dig into the node. If you can resolve it, resolve it and continue. If you cannot, mark it ⚠️ and keep walking — but note when downstream nodes depend on an unresolved one.

### Follow the real path

Trace the actual execution or data flow in order. Do not jump to the place you suspect is broken. Walk there node by node, verifying each step on the way.

### Verify each node

At every node in the flow, answer three questions:

1. What is the input? Where does it come from?
2. What transformation or side effect happens here?
3. What is the output? Does it match what the next node expects?

If any of the three is unclear, stop and investigate.

### Locate the divergence

Once every upstream node is verified, the point where expected behavior and actual behavior diverge is your target.

## Visualization

When the flow is complex, draw an ASCII or Mermaid diagram showing the path. Annotate each node with its verification status:

```
Controller.getScores(athleteId)
    │ ✓ athleteId = 1001 (Long, non-null)
    ▼
Service.queryScores(athleteId)
    │ ✓ passes athleteId correctly
    ▼
Mapper.selectScoreList(athleteId)  ← @DataScope
    │ ⚠️ DataScope may filter all records
    ▼
Result: [] (empty)
```

Only draw when it helps — not every problem needs a diagram.

## Ending the walkthrough

When the analysis is complete or blocked, summarize:

1. What was traced and verified
2. Where the breakpoint or root cause is (or what information is missing)
3. Concrete next-step options via the structured question tool

</supporting-info>
