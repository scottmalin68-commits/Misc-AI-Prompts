# ============================================================
# PROMPT NAME: Audio Meeting Analyst
# ============================================================
# Version: 1.6
# Author: Scott M  
# Last Updated: 2026-01-15
#
# Goal:
#   Transcribe audio clips (10–90 minutes) from phone recordings
#   into structured, high-signal meeting notes including summary,
#   action items, decisions, risks, and a mind‑map-style outline.
#   For clips >30 minutes, process in chunks if needed to fit AI limits.
#
# System Intent Overview:
#   This prompt defines a structured analysis workflow for meeting audio
#   or transcript data. Prioritize factual accuracy, conservative
#   inference, and practical summarization suitable for business notes,
#   not legal records. Always produce a self-contained markdown report
#   following all section headers in order, even if some sections contain
#   placeholders.
#
# Audience:
#   Tech professionals capturing informal or ad-hoc meetings
#   without dedicated recording hardware.
#
# Non-Goals:
#   - This is NOT a legal or compliance-grade transcript.
#   - This is NOT guaranteed verbatim transcription.
#   - This is NOT suitable for regulated record-keeping.
#
# Accuracy Notice:
#   BEST-EFFORT DIY solution using general AI.
#   Expected accuracy: ~70–85% on clean audio; lower for noisy/long files.
#   Professional tools (Otter.ai, Fireflies) may exceed 95%.
#   Multilingual or heavily accented audio may reduce accuracy further.
#
# AI Compatibility & Upload Limitations (Basic/Free Accounts):
#   - Grok (xAI) free tier:
#     - Audio upload: Yes, but ~25–30 min max duration / ~25–50 MB file size cap.
#     - Longer files: Rejected or truncated → split audio or use pre-transcript.
#     - Very strong at structured analysis and long-context reasoning once transcript is pasted.
#   - OpenAI's ChatGPT / GPT-4o free tier:
#     - Audio upload: Yes, but ~25 min max per file; larger/longer often blocked.
#     - Paid (Plus) lifts to ~60+ min.
#   - Anthropic's Claude 3.5 Sonnet (free tier via claude.ai):
#     - No native raw audio upload → must provide pre-transcribed text.
#     - Excellent for long text analysis (200K+ token context).
#   - Google's Gemini 1.5 Flash/Pro (free tier):
#     - Audio upload: Yes, up to ~1 hour in some cases, but inconsistent on free tier.
#     - Often requires splitting for reliability.
#
#   Prep tips for basic accounts:
#     - For 30–90 min files: Split into 15–25 min chunks (Audacity, online tools, FFmpeg).
#     - Or transcribe first with free local tools (Whisper.cpp, browser-based Whisper).
#     - Prefer full transcript paste-in when supported, to maximize continuity.
#     - If multiple chunks or sessions are processed, the final output must be a single
#       merged report covering the entire meeting, not per-chunk reports.
#
# Documentation & Prep Guide: Phone Voice Recorder Apps with Transcription (Jan 2026)
# Use your phone's built-in recorder for best results—most now offer on-device transcription.
# Export/copy transcript text and paste below to skip audio upload limits entirely.
#
# iPhone Options (iOS 18+)
# 1. Apple Voice Memos (Best Built-in)
#    - Auto transcription (iPhone 12+), edit/search, summaries (Apple Intelligence on newer models).
#    - Free, offline-capable, export text/copy.
#    - Cons: Basic speaker ID; limited languages.
#
# 2. Otter.ai (Top Overall)
#    - Real-time transcription, speaker labels, summaries.
#    - Free tier (300 min/month); Pro ~$10/month.
#
# 3. Rev Voice Recorder & Memos
#    - AI/human transcription, imports.
#    - Free app; pay for human (~$1.50/min).
#
# 4. Just Press Record / Letterly
#    - One-tap + transcription; structured notes.
#    - ~$5 one-time or subscription.
#
# 5. Notta / Transcribe - Speech to Text
#    - Import/real-time, multi-language, summaries.
#    - Free tier; Premium ~$9/month.
#
# Android Options
# 1. Google Recorder (Pixel Phones)
#    - Real-time/offline transcription, summaries (Gemini Nano), speaker labels.
#    - Free, high accuracy, offline.
#    - Pixel-exclusive for full features.
#
# 2. Samsung Voice Recorder (Galaxy Phones)
#    - Post-recording transcription (Transcript Assist), speaker labels, summaries, translation (20+ languages).
#    - Free/pre-installed on Galaxy S/A/Z series (One UI 6.1+).
#    - Cons: Post-recording only; accuracy varies with noise.
#
# 3. Otter.ai (Cross-Platform Top Pick)
#    - Real-time, speaker labels, summaries.
#    - Free tier (300 min/month); Pro ~$10/month.
#
# 4. Rev Audio & Voice Recorder
#    - AI/human transcription, imports.
#    - Free app; pay for human.
#
# 5. Dolby On
#    - Noise reduction, high-res, upload transcription.
#    - Free.
#
# Tips for Good Recordings (Aim for 85–95%+ Transcription Accuracy)
# - Quiet environment: Minimize noise/echo (soft surfaces help).
# - Position: Phone central on table, mic facing speakers (5–12 inches).
# - External mic: Clip-on/Bluetooth ($20–50) for big improvement.
# - Settings: High bitrate (44.1–48 kHz, 256+ kbps), stereo, noise reduction.
# - Test: 10–20 sec check; headphones for levels.
# - Stable: Stand/tripod; Do Not Disturb/Airplane mode.
# - Overlaps: Speak clearly; use suppression apps (Dolby On, Otter).
# - Battery: Plug in for long sessions.
#
# Other Hints
# - Workflow: Record → transcribe in-app → copy text → paste below.
# - Privacy: Notify participants; check consent laws.
# - Upgrade: Noisy? Try Rev human transcription or hardware.
# - Troubleshoot: Clean in Audacity (free), re-transcribe.
#
# Changelog:
#   v1.0 - Initial release
#   v1.1 - Added speaker attribution safeguards, inference limits,
#          ambiguity handling, and redaction guidance.
#   v1.2 - Extended for 30–90 min audio; added AI compatibility details;
#          enhanced chunking guidance and error handling.
#   v1.3 - Added Grok to compatibility list; clarified upload limits
#          for basic/free accounts; improved prep guidance.
#   v1.4 - Added iterative clarification support, TL;DR opener in summary,
#          refined action table (Priority first + Timestamp), optional Timeline,
#          Grok-specific notes, minor safety & confidence wording tweaks.
#   v1.5 - Integrated full phone voice recorder apps + transcription guide
#          into Documentation & Prep Guide section for one-stop reference.
#   v1.6 - Added top-level intent overview, stricter non-speculative
#          synthesis rules, explicit merged-output requirement for chunks,
#          standardized confidence scoring, and optional JSON export.
#
# ============================================================
#
# CONFIG (optional – for automation)
#   MODEL_CONTEXT = [Short | Medium | Long]
#   MAX_TRANSCRIPT_CHARS = [e.g., 100000]
#
# ============================================================

AUDIO / TEXT INPUT:
[Upload or link your audio file here, e.g., MP3 from phone recorder]
OR
[Paste a pre-generated transcript here — e.g., from Apple Voice Memos, Google Recorder, Samsung Voice Recorder, Otter.ai, or any .txt export]

# ============================================================
# CORE INSTRUCTIONS (copy-paste ready)
# ============================================================

1. If audio input is provided:
   - Transcribe to clean text. For long files (>30 min) or if upload limited,
     process in logical chunks (e.g., by topic breaks) and merge results into
     a single, unified report at the end.
   - Identify speakers ONLY if explicitly stated or unmistakably clear.
   - Otherwise, use neutral labels (Speaker A, Speaker B, etc.).
   - Do NOT guess speaker identities.
   - Flag any audio issues (overlap, noise, dropouts, truncation, or upload rejection).

2. Treat the transcript as RAW meeting data:
   - Expect interruptions, small talk, partial thoughts, and ambiguity.
   - Do not clean meaning beyond what is supported by content.
   - For long transcripts, prioritize high-signal sections; summarize low-relevance parts.
   - If conversation segments are disjointed or incomplete, prefer labeled gaps
     such as "[Context missing between XX:XX–YY:YY]" instead of inferring continuity.

3. All outputs must be derived from the transcript only:
   - If information is unclear, mark it as "Unclear" or "TBD".
   - Do NOT invent clarity or fill gaps with speculation.
   - Do NOT import outside knowledge of projects, products, or people.

4. Inference Rules (Strict):
   - Action owners may be inferred ONLY if clearly volunteered or assigned.
   - Do NOT assign owners based solely on who spoke most about a topic.
   - Due dates may be inferred ONLY if timeframes are explicitly referenced.
   - Priority defaults to "Medium" unless stated otherwise.

5. Decision Confidence:
   - Label each decision as:
     - Confirmed (explicit agreement)
     - Tentative (implied or conditional)
     - Disputed (conflicting viewpoints)
   - If unsure, mark as Tentative.

6. Sensitive Content Handling:
   - Redact obvious secrets (passwords, API keys, credentials).
   - Redact personal info (names, emails, phone numbers, addresses) if context suggests sensitivity.
   - Redact company identifiers if they appear as internal project names, hostnames,
     client names, or other internal references that could be sensitive.
   - Replace with [REDACTED], [REDACTED PERSONAL INFO], or [REDACTED ORG INFO]
     and flag in risks section.

7. Clarification Support:
   - If critical elements remain ambiguous after analysis (unclear assignments,
     contradictions, heavy jargon, conflicting statements), output 1–3 targeted
     clarification questions BEFORE delivering the final structured output.
   - Phrase questions as numbered, open-ended questions that can be answered
     in a follow-up message.

8. Signal Quality Directive:
   - Avoid fabricating clarity or continuity if the conversation is chaotic,
     incomplete, or noise-dominated.
   - If substantial sections are inaudible or missing, explicitly mark them
     rather than inferring decisions or action items.

9. Use STRICT markdown headings exactly as defined below.
   - Always include all sections in the final output, even if you must
     explicitly mark some content as "None" or "TBD".

# ============================================================
## 1. Audio Quality Assessment
# ============================================================

- Clarity: [Good | Fair | Poor — brief explanation]
- Length transcribed: [XX minutes]
- Speaker overlap: [Low | Medium | High]
- Estimated accuracy: [High | Medium | Low — justification]
- Processing notes: [e.g., Chunked due to length/upload limit; AI limitations encountered; pre-transcribed via phone app]

# ============================================================
## 2. Executive Summary
# ============================================================

Start with 1–2 sentence high-level overview: Why did we meet and what (if anything) was settled?

Then 5–8 bullet points covering:
- Purpose
- Attendees (or speaker count if unknown)
- Key topics
- Outcomes and next steps
- Meeting type (if inferable): [Technical | Planning | Sales | Support | General | Other]

# ============================================================
## 3. Action Items
# ============================================================

| Priority | Owner | Task Description                 | Due Date | Timestamp (approx) | Dependencies | Status | Notes |
|----------|-------|----------------------------------|----------|--------------------|-------------|--------|-------|
| Medium   | TBD   |                                  | TBD      |                    |             | Open   |       |

- Sort by Priority (High → Medium → Low) then Due Date.
- Include approximate timestamp references if available/inferable.
- Leave Owner or Due Date as TBD if not clearly specified.

# ============================================================
## 4. Key Decisions
# ============================================================

- DECISION: [What was decided]
  - Status: [Confirmed | Tentative | Disputed]
  - Rationale: [Why]
  - Impacted: [Who]
  - Evidence: [Brief quote or paraphrase]

# ============================================================
## 5. Open Questions & Risks
# ============================================================

**Open Questions**
- [Unresolved or deferred items]

**Risks**
- [Ambiguity, missing owners, sensitive data exposure, unclear scope, upload truncation, AI processing errors, large missing-context sections]

# ============================================================
## 6. Mind Map Outline
# ============================================================

(A hierarchical topic map; plain text only.)

- Main Topic 1
  - Subtopic A
    - Action / Decision / Fact
  - Subtopic B
- Main Topic 2

Rules:
- Max 5 main topics
- Max 3 levels deep
- ≤8 words per node
- Prune low-signal branches

# ============================================================
## 7. Timeline of Key Moments (optional)
# ============================================================

Include only if timestamps are available or reasonably inferable:
- 00:05 – [Brief one-line description of key moment]
- 12:40 – [etc.]

# ============================================================
## 8. Effectiveness Report
# ============================================================

- Strengths:
  - [What worked well]

- Weaknesses:
  - [Limitations encountered, e.g., long audio upload blocked on free tier]

- Confidence Score: XX / 100  
  - Rough guide:
    - 80–100 = clean + clear
    - 60–79 = moderate issues
    - <60 = heavy problems
  - Suggested approach:
    - Start from 100 and subtract for:
      - Noise / overlap issues
      - Incomplete or truncated audio
      - Large "Unclear" or "[Context missing]" segments
      - Multiple unidentified speakers or heavy ambiguity

- Recommendation:
  - If confidence <75 or >3 unclear speakers or upload failed:
    - Reprocess with cleaner audio or smaller chunks
    - OR transcribe externally then paste text
    - OR upgrade to paid tier for longer audio support
    - OR switch to professional tool (Otter.ai, Fireflies, etc.)

# ============================================================
## 9. JSON Summary (optional)
# ============================================================

Provide a compact JSON summary of key structured data, if helpful:

```json
{
  "actions": [
    {
      "priority": "Medium",
      "owner": "TBD",
      "description": "",
      "due_date": "TBD",
      "timestamp": "",
      "dependencies": "",
      "status": "Open",
      "notes": ""
    }
  ],
  "decisions": [
    {
      "decision": "",
      "status": "Tentative",
      "impacted": [],
      "evidence": ""
    }
  ],
  "risks": [
    {
      "description": "",
      "severity": "Medium"
    }
  ]
}
