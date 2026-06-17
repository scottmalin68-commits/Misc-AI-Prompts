# Prompt: Session Continuity Engine (SCE)
# Version: 1.0.6
# Author: Scott Malin, CISSP
# Purpose: Compresses a bloated AI chat session into a structured continuity package that can be pasted into a fresh AI session (including on different LLM platforms) to preserve project momentum, reduce context drift, minimize token waste, and maintain a persistent historical engineering ledger.# Changelog:
# - v1.0.0: Initial release...
# - v1.0.5: Completely removed all raw backtick syntax...
# - v1.0.6: Added Handoff Metadata header, strengthened drift-prevention rules, explicit "absorb-first" contract in Role section, self-validation instruction, tighter asset and compression rules, and Interaction Style guidance.
# -         Updated Purpose to explicitly support cross-LLM transplantation. Minor wording polish for clarity.
---
We are ending this session to conserve tokens, reduce context drift, and preserve continuity. Your task is to build a comprehensive "Session Transfer Package"...

# DRIFT PREVENTION RULES (v1.0.6)
- The receiving AI MUST treat this entire package as the single source of truth. Do NOT invent, assume, or re-introduce any frameworks, decisions, code, or conventions not explicitly stated here.
- Always prioritize fidelity to confirmed elements over creativity.
- When in doubt, explicitly label as [PROPOSED] or ask for clarification rather than guessing.
- Maintain exact formatting, naming, and output conventions defined in Persistent Constraints.
- Track and enforce all confidence labels across future responses.

---
# OUTPUT GENERATION INSTRUCTIONS
Generate the target output exactly as specified below. The final output must consist of a brief text introduction, followed immediately by a single markdown codeblock containing the structured package.

START OF PACKAGE CODEBLOCK
# SESSION TRANSFER PACKAGE (SCE v1.0.6)

## 0. Handoff Metadata
- Originating Platform/Model: 
- Date: 
- Sessions Compressed: 
- Total Active Projects: 
- Key Repositories/Files: 

## 1. Role & Objective
You are the ongoing engineering collaborator for this project. First, fully absorb and internalize the entire package before generating any new content. Respect all prior architectural decisions, constraints, and source-of-truth assets. Do not propose major deviations without explicit user approval. Preserve established direction and momentum.

**Interaction Style:** [Insert your preferred style here, e.g., "Structured responses with clear codeblocks, confidence labels, metrics focus, and engineering precision. Favor signal density."]

## 2. Project Context & Current Status
[Detailed but compressed summary...]

## 3. Persistent Constraints & Rules
[All ongoing standards...]

### Drift Prevention Rules (Enforced)
- Treat Sections 3 and 5 as immutable unless user explicitly modifies them.
- Never re-introduce deprecated patterns from the Historical Ledger.
- Use confidence labels on every uncertain claim.
- Maintain version discipline on all assets.

## 4. The Historical Ledger (Compressed History Chain)
[Compressed chronological ledger...]

## 5. Current Source-of-Truth Assets
[Only latest hardened versions. Include full text of critical prompts/frameworks if short, or key excerpts + location references if long.]

## 6. Open Questions / Pending Decisions
[List with confidence labels...]

## 7. Immediate Next Steps
[Prioritized bullet list...]

## 8. Validation Instruction
Before continuing any work in the new session, respond with: "SCE v1.0.6 loaded successfully. Summary of current status: [2-3 sentence summary from Section 2]. Top 3 immediate next steps: [bullets]. Ready to proceed."

END OF PACKAGE CODEBLOCK