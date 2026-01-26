# ==========================================================
# Prompt Name: Documentation Gap & Clarity Analyzer
# Author: Scott M
# Version: 1.4
# Last Modified: January 15, 2026
#
# Goal:
# Evaluate documentation for clarity, completeness, and usability by simulating
# readers with different skill levels and corporate roles. Identify gaps,
# assumptions, risks, and improvement opportunities — without rewriting the
# entire document.
#
# Summary:
# This prompt allows documentation owners, auditors, and reviewers to identify
# weak spots before audits, handoffs, or onboarding. It highlights missing or
# unclear instructions, structural flaws, and content that might confuse readers.
# Use it as a pre-publication or quality check for any internal document.
# ==========================================================
# -------------------------------
# WHO SHOULD USE THIS PROMPT
# -------------------------------
# Intended for:
# - Documentation owners and authors
# - IT, Security, and Operations teams
# - Managers reviewing team-facing documentation
# - Compliance, audit, or risk functions
# - Anyone maintaining policies, SOPs, runbooks, or guides
#
# Especially useful when documentation is:
# - Being handed to new or cross-functional audiences
# - Intended for non-technical staff
# - Reviewed post-incident or post-audit
# - Suspected of relying on tribal knowledge
# -------------------------------
# SUPPORTED DOCUMENTATION TYPES
# -------------------------------
# Works best with:
# - Policies, standards, and compliance documentation
# - SOPs and work instructions
# - Runbooks and playbooks
# - User guides or internal how-tos
# - Training or onboarding materials
# - Executive or management-facing summaries
#
# IMPORTANT LIMITATIONS:
# - Externally hosted AI tools cannot access internal sites or systems.
# - Do NOT reference internal URLs, SharePoint, Confluence, ServiceNow, etc.,
#   unless the relevant text is pasted here.
# - The AI cannot open attachments or follow links.
# - Any content not pasted here is considered invisible.
# - The AI may not have access to real-time data or external references; all evaluations are static and text-based only.
# - For very long documents (> ~4000-8000 words depending on AI model), consider analyzing key sections separately or in chunks to avoid context limits. Paste the most critical parts first if needed.
# -------------------------------
# SUPPORTED AI TOOLS
# -------------------------------
# Designed for general-purpose large language models supporting long-form analysis.
# Known compatible tools:
# - ChatGPT — https://chat.openai.com
#   Strengths: Structured analysis and persona-based reasoning.
# - Claude — https://claude.ai
#   Strengths: High contextual precision; ideal for policies and compliance docs.
# - Perplexity — https://www.perplexity.ai
#   Strengths: Strong summarization; ensure focus stays on pasted content.
# - Poe — https://poe.com
#   Strengths: Access to multiple backend models; results vary by model.
# - Grok — https://grok.x.ai
#   Strengths: Logical reasoning and complex query handling; suitable for detailed gap identification.
#
# No browsing, plugins, or integrations are required. All analysis is based solely
# on the provided text.
# -------------------------------
# SYNTAX & USAGE INSTRUCTIONS
# -------------------------------
# Follow this exact structure when using the prompt.
# STEP 1: Choose Skill Level to Emulate
# (Determines assumed knowledge and expected clarity.)
# Choose ONE:
# - Beginner – First exposure to the topic, zero context.
# - Basic Working Knowledge – Some familiarity, not fluent in process details.
# - Intermediate – Regular user of similar documentation.
# - Advanced – Skilled practitioner, expects precision.
# - Expert – Deep subject matter knowledge, expects completeness and accuracy.
# STEP 2: Choose Persona(s) to Emulate
# List one or more personas explicitly. The AI analyzes only from their view.
# e.g., 'Executive, Auditor / Compliance Reviewer'
# STEP 3: (Optional) Choose Focus Area
# Use ONE if you want the AI to weight its evaluation:
# - Compliance / Risk
# - Operations / Efficiency
# - Training / Onboarding
# - User Experience / Accessibility
# STEP 4: (Optional) Provide Context Notes
# Add any intended audience details, operational context, or known weak points.
# STEP 5: Paste Full Documentation
# Always include the entire text to avoid false gap detection. For very long docs, paste priority sections and note "analyze this section first" if needed.
#
# If any required field (Skill Level, Persona, Documentation) is missing or unclear, politely ask the user to provide it before proceeding.
# -------------------------------
# PERSONAS TO EMULATE
# -------------------------------
# Common corporate readers:
# - Executive:
#   Focuses on high-level outcomes, accountability, risk, and intent.
#   Expects concise summaries and impact statements.
# - Manager / Team Lead:
#   Needs clarity around ownership, decisions, escalation, and dependencies.
# - Non-Technical Employee:
#   Understands business goals, not technical jargon. Needs definitions and examples.
# - New Hire / Onboarding Employee:
#   Lacks internal context. Needs background, sequencing, and explicit assumptions.
# - Technical Practitioner / SME:
#   Prioritizes accuracy, completeness, and unambiguous instructions.
# - Auditor / Compliance Reviewer:
#   Looks for traceability, evidence of control coverage, and procedural consistency.
# -------------------------------
# USAGE EXAMPLES
# -------------------------------
# Example 1: Reviewing an Incident Response Runbook
# ---------------
# Target Skill Level:
# Intermediate
# Persona(s) to Emulate:
# Technical Practitioner / SME, Auditor / Compliance Reviewer
# Optional Focus Area:
# Compliance / Risk
# Context Notes (Optional):
# This runbook is used during major incidents; regulatory reporting deadlines apply.
# Documentation to Analyze:
# [Paste your full runbook text here]
# ---------------
#
# Example 2: Onboarding Guide for Non-Technical Staff
# ---------------
# Target Skill Level:
# Beginner
# Persona(s) to Emulate:
# New Hire / Onboarding Employee, Non-Technical Employee
# Optional Focus Area:
# Training / Onboarding
# Context Notes (Optional):
# Intended for sales and HR teams with no prior IT access experience.
# Documentation to Analyze:
# [Paste your full onboarding guide text here]
# ---------------
# -------------------------------
# INPUT SECTION (REQUIRED)
# -------------------------------
# --------------- BEGIN REQUIRED INPUT ---------------
# Target Skill Level:
# [INSERT HERE]
# Persona(s) to Emulate:
# [INSERT HERE]
# Optional Focus Area:
# [INSERT HERE]
# Context Notes (Optional):
# [INSERT NOTES HERE]
# Documentation to Analyze:
# [PASTE FULL CONTENT HERE]
# --------------- END REQUIRED INPUT -----------------
# -------------------------------
# ANALYSIS INSTRUCTIONS
# -------------------------------
Act as the selected persona(s) with the specified skill level and optional focus area.
Review the documentation as though you are using it for real decisions or tasks.
Identify and report on:
1. Missing Information
   - Unanswered questions, assumptions, or unstated knowledge.
2. Clarity Gaps
   - Vague terms, undefined acronyms, incomplete steps, or inconsistent phrasing.
3. Structural or Sequencing Issues
   - Poor organization, unclear flow, missing introductions, or steps out of logical order.
4. Usability & Practicality
   - Points where a reader may hesitate, misinterpret, or fail to complete an action.
5. Risk & Impact
   - Operational, security, compliance, safety, or legal implications if misunderstood. Flag any that appear high-urgency (e.g., safety violations, regulatory non-compliance).
6. Versioning and Maintenance Gaps
   - Missing update history, revision dates, owner contacts, approval workflow, change log, or procedures for keeping the document current.
Also:
- Reference short snippets or examples where issues appear.
- Prioritize issues by *impact* rather than quantity (focus on high-risk first).
- Rank them High / Medium / Low for significance.
# -------------------------------
# OUTPUT FORMAT
# -------------------------------
Provide results in these sections:
- Persona & Skill Level Used
- Optional Focus Area (if provided)
- Quality Scores:
  - Clarity: [1–5]
  - Completeness: [1–5]
  - Usability: [1–5]
- Strengths Noted (brief highlights of clear or complete elements)
- Key Gaps Identified (brief summary list, grouped by category)
- Examples of Confusing or Missing Content (with referenced excerpts)
- Risk or Impact of These Gaps (rank H/M/L; note any urgent flags)
- Top 3 Most Critical Issues (with short justification)
- Actionable Recommendations (specific, concise guidance; focus on fixes, not rewrites)
# Do NOT rewrite the document unless explicitly asked.
# All findings should focus on actionable gaps, not stylistic or tone preferences.
# If the document appears safety-critical or compliance-heavy and gaps are severe, include a note suggesting immediate professional review.
