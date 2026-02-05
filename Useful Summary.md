TITLE: Useful Summary (Action-Oriented, Content-Aware)
VERSION: 1.5
AUTHOR: Scott M

## Goal
Produce a concise, decision-focused summary while minimizing the risk of misinterpretation.

This prompt prioritizes usefulness, transparency, and safety over completeness.

---

## Step 1: Content Detection
Before summarizing, attempt to identify the content type.

If the content type is **clear**, proceed.

If the content type is **unclear or mixed in a way that affects decisions, risk, or compliance**:
- Ask the user **one concise clarifying question** (maximum one sentence).
- If no response is available, proceed in low-confidence mode.

---

## Step 2: Summarization Rules

Summarize the input by keeping only what materially affects decisions, priorities, or actions.

### Keep
- Action items (what needs to be done and by when)
- Decisions that were made (explicit or clearly implied)
- Numbers that matter (deadlines, costs, limits, metrics)
- Risks, warnings, or constraints
- Ownership (who is responsible for what)
- Anything that directly affects me or changes what I should do

### Skip
- Background context I likely already know
- Repetition or illustrative examples
- Long explanations of "why" unless they change actions or priorities
- Corporate speak, filler, or hedging language

### Special Rules
- Do NOT guess ownership, deadlines, or intent.
- Flag ambiguity instead of resolving it.
- Preserve legal, security, or compliance constraints even if subtle.

---

## Output Format

### Confidence Score
At the very top, include:

**Confidence: XX / 100**

Base the score on:
- Clarity of content type
- Explicitness of actions, decisions, and ownership
- Degree of ambiguity or missing information
- Risk of misinterpretation

---

### Confidence-Driven Behavior

#### 80–100 (High Confidence)
- Use maximum compression
- Assume shared context
- Minimal explanation

#### 50–79 (Medium Confidence)
- Slightly increased verbosity
- Explicitly note ambiguities or assumptions
- Highlight areas that may need confirmation

#### 0–49 (Low Confidence)
- Prioritize safety over compression
- Avoid interpretation or inference
- Clearly state that the content could not be processed with high confidence
- Provide:
  - A limited, cautious summary of **only explicitly stated facts**
  - A short section titled **“Source Excerpt (for reference)”** containing relevant portions of the original content
- Include a brief warning that decisions should not be made without reviewing the source directly

---

### Summary Body
- Use bullets by default
- Put the most critical information first
- Separate sections when applicable:
  - **Do this now**
  - **Just FYI / Future consideration**

If something does not clearly affect decisions, priorities, or actions, leave it out.

---

## Recommended AI Engines (Best → Worst)
1. GPT-4.1 / GPT-5.x  
2. Claude 3.5 Sonnet  
3. Gemini Advanced  
4. Smaller or local models

---

## Changelog

### v1.5
- Added numeric confidence score (0–100)
- Introduced confidence-driven verbosity scaling
- Implemented safe low-confidence handling with source visibility
- Prioritized harm reduction over aggressive interpretation

### v1.4
- Added categorical Confidence Flag
- Required justification for lower confidence outputs

### v1.3
- Embedded AI engine recommendations and changelog

### v1.2
- Added content-type detection with clarifying fallback

### v1.1
- Added ambiguity handling and legal/security safeguards

### v1.0
- Initial action-oriented summarization logic
