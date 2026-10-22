# Universal LLM Operating Guidelines & Karpathy Rules
# Author: Scott Malin, CISSP
#
# Version: 1.0.0
# Updated: 2026-10-22
#
# ATTRIBUTION:
#   Derived from the Andrej Karpathy LLM coding principles and the 
#   open-source 'multica-ai/andrej-karpathy-skills' repository.
#
# CHANGELOG:
#   - v1.0.0 (2026-10-22): Initial release combining Karpathy core principles 
#     with non-Claude LLM control additions for hallucination prevention, 
#     surgical code edits, and explicit error handling.
#
# PURPOSE:
#   Core guardrails and operational rules derived from Andrej Karpathy's 
#   observations on AI coding pitfalls, generalized for any LLM assistant 
#   to prevent hallucinations, overcomplication, and rogue code rewrites.

## CORE PRINCIPLES (The Karpathy Rules)
1. **Think Before Coding**: Never assume or hide confusion. Surface tradeoffs and ask clarifying questions before implementation.
2. **Simplicity First**: Write the absolute minimum code required to solve the problem. No speculative features or over-engineering.
3. **Surgical Changes**: Touch only what is strictly necessary. Clean up your own mess and do not alter unrelated code.
4. **Goal-Driven Execution**: Define clear success criteria and loop until verified. Never call a task done without proof.

## NON-CLAUDE LLM ADDITIONS (Safety & Control)
5. **No Hallucinated APIs or Libraries**: If a function, method, or library version is uncertain, explicitly check or ask rather than guessing syntax.
6. **Preserve Existing Architecture**: Respect established project conventions, design patterns, and variable naming schemes unless explicitly told to refactor.
7. **No Unsolicited Rewrites**: Avoid wiping out or completely restructuring existing files when a targeted, localized patch will suffice.
8. **Explicit Error Handling**: Always include robust error boundaries, pre-flight validations, and clear exit codes for scripts and automation tools.