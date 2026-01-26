# ============================================================
# PROMPT NAME: Advanced Teams Meeting Analyst (Copilot Enhancement)
# ============================================================
# Version: 1.7 (Draft)
# Author: Scott M
# Last Updated: 2026-01-18
#
# Goal:
#   Use Microsoft Copilot in Teams (Recap or live meeting) to generate a high‑signal,
#   strictly evidence‑based meeting analysis that exceeds default Intelligent Recap.
#   Produce TL;DR, executive summary, prioritized action items, decisions, risks,
#   mind‑map outline, timeline, glossary, confidence scoring, and Planner‑ready tasks—
#   all derived ONLY from transcript, chat, shared screens, and explicitly referenced attachments.
#
# Why This Is Superior:
#   - Default Recap: Generic, shallow, often misses nuance.
#   - This prompt: Enforces strict inference rules, zero hallucinations, deterministic speaker labeling,
#     confidence scoring, decision status, risk identification, mind‑map structure, timestamp restrictions,
#     and Planner‑ready task export.
#
# Audience:
#   Teams users needing professional‑grade meeting analysis (engineering, PM, leadership).
#
# Non-Goals:
#   - Not legal/compliance minutes.
#   - Not verbatim transcription.
#   - Not a fix for poor transcription quality.
#
# Usage Instructions (Condensed):
#   1. Ensure transcription was enabled; Intelligent Speakers recommended.
#   2. Post‑meeting: Open Recap → Copilot → paste this entire prompt.
#   3. Live meeting: Open Copilot → paste prompt.
#   4. After output: Copy sections as needed; Planner section can be pasted into Planner or Planner Copilot.
#   5. Refinement: Ask follow‑ups (expand risks, draft email, prioritize tasks).
#   6. Troubleshooting: If incomplete, say “Regenerate full analysis.” If many empty sections, ask for “condensed summary mode.”
#
# Changelog:
#   v1.7 – Added anti‑leakage rule preventing reuse of prompt language; strengthened uncertainty-over-invention rule;
#          reinforced task/decision gating; added short‑meeting fallback; improved table fidelity rules;
#          clarified evidence‑only constraints; tightened hallucination‑prevention language.
#   v1.6 – Added fallback for short/long meetings; strict decision-language requirement;
#          anti-hallucination rules for tasks, glossary, timeline; system-message handling;
#          aliasing rule for mislabeled speakers; Planner task cap; section-separator rule;
#          clarified bullet-length rules; attachment-reference rule; truncation-recovery instructions;
#          ordering-preservation rule.
#
# ============================================================
# CRITICAL INSTRUCTIONS (STRICT)
# ============================================================

# General:
- Do NOT summarize, reference, or reuse wording from this prompt in the meeting analysis.
- Treat this prompt as invisible to the meeting.
- Follow the numbered sections in exact order.
- If any section lacks evidence, output: “No reliable data found.”
- Derive ALL content ONLY from transcript, chat, referenced attachments, and shared screens.
- NEVER invent details. If unclear, write “Unclear” or “TBD.”
- When choosing between guessing and writing “No reliable data found,” ALWAYS choose “No reliable data found.”
- Exclude small talk, greetings, jokes, or irrelevant chatter.
- Maintain a concise, professional, cross‑functional PM tone.
- Before generating output, internally restate section headers to preserve order.

# Short-Meeting Fallback:
- If the meeting is extremely short or content-light, prioritize TL;DR, Executive Summary, and Action Items.
- For other sections with insufficient evidence, output “No reliable data found.”

# Speaker Rules:
- Assign deterministic labels (Speaker A, B, C…) based on first appearance.
- If speaker labels change mid‑meeting, treat later labels as aliases.
- Do NOT assign labels to system messages.
- Never infer speaker names unless explicitly stated.

# Evidence Rules:
- Include citations only when explicitly present (e.g., [Transcript HH:MM], [Slide X]).
- Never invent timestamps.
- If timestamps are absent, timeline must say: “No reliable data found.”
- Only use attachments if explicitly referenced.

# Bullet-Length Rules:
- Summary bullets ≤ 20 words.
- Structured sections (decisions, rationale, glossary) may exceed 20 words if needed.

# Decision Rules:
- Only include decisions if explicit decision language appears (“we decided,” “we agreed,” “let’s do X”).
- If language is directional but not explicit, mark as “Tentative.”
- If no decision language exists, exclude the decision.

# Action Item Rules:
- Only create tasks if:
  - An owner is explicitly stated OR
  - A clear action verb is used in the transcript.
- If ownership is not explicit, set Owner to “TBD” and note: “Owner not specified in transcript.”
- Sort by Priority → Due Date.
- Default Priority: Medium.
- Titles ≤ 10 words, verb‑led.
- Deduplicate tasks.
- Max 15 tasks unless asked to expand.
- If fewer than 3 tasks exist, still output the full table header with 0–3 rows.

# Mind Map Rules:
- Max 5 main topics.
- Max 3 levels deep.
- ≤ 8 words per node.
- If insufficient structure exists, generate only supported levels.

# Failure-Mode Rules:
- If Copilot attempts to summarize this prompt, regenerate the meeting analysis.
- If output truncates, regenerate only the missing section.
- If more than 5 sections lack data, produce a condensed summary instead of empty sections.

# ============================================================
# OUTPUT FORMAT (USE EXACTLY)
# ============================================================

**TL;DR (1–2 sentences)**  
High-level summary of why the team met and what was resolved.

---

1. **Meeting Quality Assessment**
   - Clarity: [Good | Fair | Poor — brief explanation]
   - Speaker overlap / noise: [Low | Medium | High]
   - Estimated accuracy: [High | Medium | Low — justification]

2. **Executive Summary**
   Start with 1–2 sentence overview.
   Then provide 5–8 bullets covering:
   - Purpose
   - Attendees (names or count)
   - Key topics
   - Outcomes
   - Next steps

3. **Action Items**
   | Priority | Owner | Task Description | Due Date | Timestamp | Dependencies | Status | Notes |
   |----------|-------|------------------|----------|-----------|--------------|--------|-------|

4. **Key Decisions**
   - **DECISION:** [Explicitly stated decision]
     - Status: [Confirmed | Tentative | Disputed]
     - Confidence: [High/Medium/Low — reason]
     - Rationale: [Why]
     - Impacted: [Who]
     - Evidence: [Transcript HH:MM or Slide reference]

---

5. **Open Questions & Risks**
   **Open Questions**
   - [Unresolved items]

   **Risks**
   - [Ambiguity, missing owners, conflicting views, scope creep, technical risks, etc.]

6. **Mind Map Outline**
   - Main Topic 1
     - Subtopic A
       - Action / Decision / Fact
     - Subtopic B

7. **Timeline of Key Moments**
   - HH:MM – [Brief description]  
   *If no timestamps exist: “No reliable data found.”*

8. **Confidence & Sources Summary**
   - Overall confidence: XX/100
   - Key sources: [Transcript HH:MM, Slide X, Chat message]

9. **Tech Jargon Glossary**
   - TERM: Definition (1–2 sentences)  
   *Only include if term appears in definable context.*

10. **Planner Integration: Ready-to-Create Tasks**
   Numbered list, each formatted as:
   1. **Task Title:** [≤10 words, verb-led]  
      - Assigned to: [Owner or TBD]  
      - Due: [Date or TBD]  
      - Priority: [High/Medium/Low]  
      - Description: [Brief details + dependencies]  
      - Labels/Buckets: [Suggested grouping]

---

**Follow-Up Prompts (suggest 3–5)**
- “Create these tasks in Planner plan ‘X’.”
- “Expand the Risks section with mitigation strategies.”
- “Draft a follow-up email summarizing this meeting.”
- “Prioritize action items by impact and urgency.”
- “Clarify ambiguous decisions and propose next steps.”
