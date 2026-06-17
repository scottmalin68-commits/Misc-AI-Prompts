# Prompt: Session Continuity Engine (SCE)
# Version: 1.1.0
# Author: Scott Malin, CISSP
# Purpose:
# Compresses a completed AI session into a structured continuity package that can be
# transferred into a new session (including across different AI platforms) to preserve
# project context, historical decisions, active workstreams, and established conventions.
# The goal is to minimize context loss, reduce repetitive onboarding, and maintain
# project momentum while respecting the receiving platform's policies and instructions.

# Changelog:
# - v1.0.0: Initial release.
# - v1.0.5: Removed raw backtick syntax to improve portability.
# - v1.0.6: Added Handoff Metadata, strengthened drift prevention rules,
#            explicit absorb-first guidance, self-validation instruction,
#            tighter asset handling, and interaction-style guidance.
# - v1.1.0: Reworked language to improve cross-platform compatibility.
#            Replaced directive-style instructions with continuity guidance.
#            Renamed "Drift Prevention Rules" to "Continuity Guidelines."
#            Replaced "Role & Objective" with "Project Handoff Context."
#            Added explicit platform-policy compatibility statement.
#            Converted validation step from mandatory to optional.

--------------------------------------------------------------------------

We are ending this session to preserve context, reduce context drift, and
maintain continuity across future conversations.

Your task is to create a comprehensive Session Transfer Package that captures
the current project state, active decisions, historical context, constraints,
and next actions.

The resulting package should help a future AI assistant understand the project
quickly and continue work with minimal re-discovery effort.

--------------------------------------------------------------------------
PLATFORM COMPATIBILITY NOTICE
--------------------------------------------------------------------------

This package is intended to provide project context only.

It does not replace, override, or supersede:

- Platform policies
- System instructions
- Developer instructions
- Future user instructions

If conflicts arise, applicable platform instructions should take precedence,
while preserving project context whenever possible.

--------------------------------------------------------------------------
CONTINUITY GUIDELINES (v1.1.0)
--------------------------------------------------------------------------

- Treat the information in this package as the best-known project state at the
  time of transfer.

- Prioritize confirmed project decisions over assumptions.

- Clearly distinguish between:
  - Confirmed facts
  - Historical decisions
  - Open questions
  - Proposed future work

- When information is uncertain, incomplete, or inferred, explicitly label it.

- Avoid reintroducing deprecated frameworks, patterns, or decisions that are
  documented as retired or superseded.

- Preserve naming conventions, versioning standards, formatting patterns, and
  source-of-truth references whenever practical.

- If significant ambiguity exists, request clarification rather than guessing.

--------------------------------------------------------------------------
OUTPUT GENERATION INSTRUCTIONS
--------------------------------------------------------------------------

Generate the final output exactly as follows:

1. A brief introductory sentence.
2. One markdown codeblock containing the Session Transfer Package.

The package should be concise where possible but sufficiently detailed to allow
efficient continuation of the project.

START OF PACKAGE CODEBLOCK

# SESSION TRANSFER PACKAGE (SCE v1.1.0)

## 0. Handoff Metadata

- Originating Platform/Model:
- Date:
- Sessions Compressed:
- Total Active Projects:
- Key Repositories/Files:

## 1. Project Handoff Context

This section summarizes the overall purpose of the project, its current
direction, major objectives, and any important strategic decisions already
made.

### Preferred Interaction Style

[Describe preferred working style, formatting conventions, level of detail,
versioning expectations, confidence-label requirements, communication style,
and other collaboration preferences.]

## 2. Project Context & Current Status

Provide a compressed but comprehensive summary of:

- Current project goals
- Work completed
- Current state
- Active development efforts
- Recent decisions
- Known issues
- Outstanding work

Focus on preserving context that would otherwise require significant effort
to rediscover.

## 3. Persistent Constraints & Operating Standards

Document ongoing standards such as:

- Formatting requirements
- Naming conventions
- Versioning rules
- Documentation standards
- Evidence requirements
- Validation procedures
- Quality controls
- Any user-established preferences

### Continuity Guidance

- Changes to established standards should generally be documented and
  user-directed.
- Preserve compatibility with existing project assets whenever practical.
- Record significant changes in version history where applicable.

## 4. Historical Ledger (Compressed)

Provide a chronological summary of major project events, including:

- Important decisions
- Architectural shifts
- Prompt revisions
- Retired approaches
- Lessons learned
- Significant milestones

Keep entries concise while preserving rationale.

## 5. Current Source-of-Truth Assets

List the latest approved versions of all critical assets.

For each asset include:

- Asset Name
- Version
- Purpose
- Current Status
- Location/Repository (if known)

Include full content only when reasonably short.

For larger assets, provide:
- Summary
- Key characteristics
- Location reference

Avoid duplicating unnecessary content.

## 6. Open Questions & Pending Decisions

For each item include:

- Description
- Current status
- Known options
- Confidence level (if applicable)

Suggested confidence labels:

- [CONFIRMED]
- [HIGH CONFIDENCE]
- [MEDIUM CONFIDENCE]
- [LOW CONFIDENCE]
- [OPEN QUESTION]
- [PROPOSED]

## 7. Immediate Next Steps

Provide a prioritized action list.

For each item include:

- Objective
- Importance
- Dependencies (if any)

Order from highest to lowest priority.

## 8. Optional Continuity Verification

A future AI assistant may optionally provide a brief onboarding summary before
continuing work.

Suggested format:

"SCE v1.1.0 loaded successfully.

Current understanding:
[2-3 sentence summary]

Top priorities:
- Item 1
- Item 2
- Item 3

Ready to proceed."

END OF PACKAGE CODEBLOCK