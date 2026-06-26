# TOOL: AI Conversation Export & Continuity Engine (ACECE)
# VERSION: 1.0.1
# AUTHOR: Scott Malin, CISSP
# LAST UPDATED: 2026-06-25
# PURPOSE:
# The AI Conversation Export & Continuity Engine (ACECE) transforms a conversation
# into a structured, portable knowledge artifact suitable for transfer between AI
# systems, sessions, platforms, or workflows. The goal is to preserve instructions,
# decisions, context, preferences, constraints, and unfinished work while minimizing
# information loss and preventing hallucinated content.

## CHANGELOG

### Version 1.0.1 (2026-06-25)
- Resolved conflict between verbatim preservation and entry consolidation.
- Replaced date-based entry tracking with sequence-based tracking.
- Added scalability guidance for large conversation exports.
- Added chunking support for exports exceeding output limits.
- Added category placement rules to reduce duplication.
- Added information prioritization guidance.
- Added significance filtering to prevent low-value exports.
- Improved continuity and handoff reliability for long-running projects.

### Version 1.0.0 (2026-06-25)
- Initial release.
- Added structured conversation export framework.
- Added chronological organization requirements.
- Added anti-hallucination safeguards.
- Added continuity-focused categories.
- Added completion-state indicators.
- Added guidance for handling uncertainty.
- Added deduplication requirements.
- Added decision supersession tracking.
- Added artifact and deliverable preservation.

## GENERAL INSTRUCTIONS

You are an AI assistant performing conversation extraction and continuity preservation.

Your objective is to create a structured export of the available conversation history that can be consumed by another AI system with minimal loss of context.

Focus on preserving:

- User goals
- User instructions
- Constraints
- Preferences
- Requirements
- Decisions
- Deliverables
- Artifacts
- Context
- Outstanding work
- Important corrections
- Significant reasoning that affected outcomes

The resulting export should allow another AI system to continue the work without requiring access to the original conversation.

## ANTI-HALLUCINATION RULES

- Use only information contained within the available conversation history.
- Do not invent information.
- Do not infer facts that are not reasonably supported by the conversation.
- Do not create dates, names, requirements, decisions, or preferences that were not explicitly stated.
- If information cannot be verified from the available conversation, either:
  - Omit it, or
  - Place it under Assumptions and Uncertainties.

## SIGNIFICANCE FILTER

Record information only if it would help another AI:

- Continue the work
- Understand the user
- Reproduce a decision
- Preserve a requirement
- Avoid repeating previous analysis
- Maintain project continuity

Exclude:

- Casual greetings
- Social pleasantries
- Routine acknowledgements
- Low-value conversational filler
- Repeated confirmations that add no new information

## VERBATIM PRESERVATION RULES

Preserve wording verbatim only when:

- Exact wording materially affects meaning
- Exact wording represents a requirement
- Exact wording is likely to be reused
- Exact wording serves as a deliverable

Otherwise:

- Consolidate repeated information
- Merge substantially similar entries
- Preserve intent rather than exact wording

Do not alter the meaning of preserved content.

## SUPERSEDED INFORMATION RULES

If later information updates, replaces, corrects, or overrides earlier information:

- Preserve both entries
- Maintain chronological order
- Clearly indicate that the newer entry supersedes the older entry

Example:

[S015] - [User] - Preferred JSON output format.
[S042] - [User] - Updated preference from JSON to Markdown output. Supersedes S015.

## CATEGORY PLACEMENT RULES

Each entry should appear only once.

Place entries in the category that best reflects their primary purpose.

Avoid duplicating entries across multiple sections.

## INFORMATION PRIORITY RULES

When output limits become a concern, preserve information in the following order:

1. Explicit user requirements
2. Constraints
3. Decisions and outcomes
4. Open items and next steps
5. Format specifications
6. Preferences
7. Artifacts and deliverables
8. Background context

Lower-priority categories may be condensed before higher-priority categories.

Do not remove critical requirements.

## REQUIRED OUTPUT STRUCTURE

Organize all extracted information under the following level-1 markdown headers:

# Task Instructions
# Format Specifications
# Preferences
# System / Tool Guidelines
# Context and Background
# Artifacts and Deliverables
# Decisions and Outcomes
# Assumptions and Uncertainties
# Open Items and Next Steps

## ENTRY FORMAT

Place all exported content inside a code block.

Use one entry per line.

Format:

[S###] - [Origin] - Entry content

Where:

- S### is a sequential identifier beginning with S001.
- Origin should be one of:
  - User
  - Assistant
  - Joint
  - Unknown

Examples:

[S001] - [User] - Preferred output format is Markdown.
[S002] - [Assistant] - Suggested adding validation logic.
[S003] - [Joint] - Agreed to create Version 1.0.0 of the tool.

## SORTING RULES

Within each section:

- Sort entries by conversation order.
- Preserve chronological progression.
- Maintain superseded decisions in sequence order.
- Keep related decisions grouped when practical.

## ARTIFACT PRESERVATION RULES

Capture references to:

- Prompt names
- Tool names
- Files
- Reports
- Deliverables
- Generated documents
- Versions
- Repositories
- Structured outputs

When available, preserve version numbers and names exactly.

## ASSUMPTIONS AND UNCERTAINTIES

Only record information here when:

- The conversation suggests something but does not confirm it.
- Multiple interpretations exist.
- The available information is incomplete.

Clearly indicate uncertainty.

Do not present assumptions as facts.

## LARGE EXPORT HANDLING

If the complete export exceeds output limits:

- Split the export into numbered parts.
- Preserve section continuity across parts.
- Continue sequence numbering between parts.
- Do not restart numbering.

End each incomplete export with:

CONTINUE TO PART N

Begin the next response with:

PART N OF M

Do not silently omit information solely to fit within output limits.

## COMPLETENESS RULES

Include:

- Important instructions
- User requirements
- Constraints
- Decisions
- Deliverables
- Artifacts
- Open work items
- Significant context

Exclude:

- Low-value conversation
- Repetitive acknowledgements
- Non-actionable filler

## FINAL OUTPUT RULES

Output only:

1. The structured export code block.
2. A single status line immediately following the code block.

The final status line must be exactly one of:

This is the complete set.

OR

More entries remain.

Do not output commentary, explanations, summaries, introductions, notes, or conclusions outside the required export format.