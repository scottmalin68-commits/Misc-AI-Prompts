# Prompt: Session Continuity Engine (SCE)
# Version: 1.0.2
# Author: Scott M.
# Purpose: Compresses a bloated AI chat session into a structured continuity package that can be pasted into a fresh AI session to preserve project momentum, reduce context drift, minimize token waste, and maintain a persistent historical engineering ledger.

# Changelog:
# - v1.0.0: Initial release. Implemented Role, Project Status, Ledger Chain, Asset Capture, and Next Steps parameters. Added multi-session nesting support.
# - v1.0.1: Added historical compression rules, persistent constraints, open questions, prioritization framework, confidence labeling, and archival pruning guidance.
# - v1.0.2: Fixed output execution bugs, resolved codeblock nesting conflicts, and hardened ledger compression logic.

---

We are ending this session to conserve tokens, reduce context drift, and preserve continuity. Your task is to build a comprehensive "Session Transfer Package" that can be pasted into a brand-new AI session so work can continue seamlessly without losing project history, architectural reasoning, or operational context.

Analyze the conversation history carefully. 

Your goal is NOT to preserve every message.

Your goal IS to preserve:
- finalized systems
- hardened logic
- confirmed decisions
- important reasoning
- unresolved issues
- active workstreams
- operational constraints
- current source-of-truth assets

You should intentionally discard:
- repetitive brainstorming
- obsolete versions
- superseded logic
- duplicate discussion
- casual conversation
- abandoned approaches unless strategically important

---

# CONTEXT PRIORITIZATION RULES

Prioritize extraction in this order:
1. Finalized systems and architectures
2. Current active work
3. Explicit user decisions
4. Hardened logic and stable frameworks
5. Operational constraints and formatting standards
6. Outstanding issues and unresolved risks
7. Historically important breakthroughs

Deprioritize: duplicate discussion, speculative tangents, obsolete iterations, conversational filler, and temporary abandoned experiments.

---

# HISTORICAL COMPRESSION RULES

To prevent recursive context bloat:
- Preserve FULL detail for the current session.
- Compress older sessions into a single, high-signal engineering changelog.
- Do NOT nest previous transfer packages verbatim. Extract their core data points, append the current session's milestones, and merge them into a single continuous timeline under Section 4.
- Eliminate repetitive history and duplicate summaries.

---

# ANTI-HALLUCINATION RULES

Do NOT invent decisions, files, frameworks, features, milestones, codebases, or conclusions. If something was discussed but never finalized, explicitly label it.

Use these confidence labels where appropriate:
- [CONFIRMED]
- [PROPOSED]
- [UNVERIFIED]
- [REJECTED]
- [DEPRECATED]

If uncertainty exists, say so directly instead of guessing.

---

# OUTPUT GENERATION INSTRUCTIONS

Generate the target output exactly as specified below. The final output must consist of a brief text introduction, followed immediately by a single markdown codeblock containing the structured package.

### Target Output Structure to Generate:

[Brief introductory text stating that the session transfer package is ready]

```markdown
# SESSION TRANSFER PACKAGE (SCE v1.0.2)

## 1. Role & Objective
[Instruct the next AI to act as the ongoing engineering collaborator for this project. Tell it to absorb history first, avoid immediate code generation, understand project continuity before making changes, and preserve established architectural direction/constraints.]

## 2. Project Context & Current Status
[Provide a detailed but compressed summary of what the project/system is, what has been completed, current operational state, active development areas, current objectives, and major architectural direction. High-signal info only.]

## 3. Persistent Constraints & Rules
[Capture all ongoing operational standards, including formatting rules, markdown preferences, naming conventions, workflow expectations, tone requirements, anti-hallucination expectations, validation requirements, and prohibited behaviors.]

## 4. The Historical Ledger (Compressed History Chain)
[Create a compressed engineering-style chronological ledger of major decisions, important breakthroughs, critical pivots, architectural evolution, rejected approaches, and completed milestones. Newer sessions get more detail; older sessions get highly compressed. No duplication.]

## 5. Current Source-of-Truth Assets
[Include ONLY the latest hardened versions of prompts, frameworks, scripts, systems, templates, logic structures, or operational models. Do NOT include obsolete or buggy versions.]

## 6. Open Questions / Pending Decisions
[List unresolved items like uncertain architecture decisions, debated features, unvalidated assumptions, or pending integrations. Clearly separate confirmed decisions, proposed ideas, and unresolved discussions using the confidence labels.]

## 7. Immediate Next Steps
[Provide a prioritized bullet list of immediate tasks, active goals, pending refinements, validation work, implementation priorities, and unresolved blockers for the next session.]