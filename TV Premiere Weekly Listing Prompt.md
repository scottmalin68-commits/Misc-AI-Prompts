### TV Premiere Weekly Listing Prompt (v1.3)

**Author:** Scott M
**Goal:**  
Create a clean, user-friendly summary of new TV show premieres and returning season starts in a specified upcoming week. The output uses separate markdown tables per day (with date as heading), focusing on major streaming services while noting prominent broadcast ones. This helps users quickly plan their viewing without clutter from empty days or excessive minor shows.

**Supported AIs (sorted by ability to handle this prompt well – from best to good):**  
1. Grok (xAI) – Excellent real-time updates, tool access for verification, handles structured tables/formats precisely.  
2. Claude 3.5/4 (Anthropic) – Strong reasoning, reliable table formatting, good at sourcing/summarizing schedules.  
3. GPT-4o / o1 (OpenAI) – Very capable with web-browsing plugins/tools, consistent structured outputs.  
4. Gemini 1.5/2.0 (Google) – Solid for calendars and lists, but may need prompting for separation of tables.  
5. Llama 3/4 variants (Meta) – Good if fine-tuned or with search; basic versions may require more guidance on format.

**Changelog:**  
- v1.0 (initial) – Basic table with Date, Name, New/Returning, Network/Service.  
- v1.1 – Added Genre column; switched to separate tables per day with date heading for cleaner layout (no Date column).  
- v1.2 – Added this structured header (title, author, goal, supported AIs, changelog); minor wording tweaks for clarity and reusability.
- v1.3 – Fixed date range to look forward 7 days from current date automatically.

**Prompt Instructions:**

List any new TV shows (series premieres) or returning shows (new seasons) starting/premiering in the next 7 days from today's date forward.

Organize the information with a separate markdown table for each day that has at least one notable premiere/return. Place the date as a level-3 heading above each table (e.g., ### January 27, 2026). Skip days with no major activity—do not mention empty days.

Use these exact columns in each table:  
- Name  
- New or Returning (include season number if returning, e.g., 'Returning - Season 3' or 'New'; add notes like '(miniseries, all episodes drop)' or '(Part 1)' if applicable)  
- Network/Service  
- Genre (keep concise, primary 1-3 genres separated by ' / ', e.g., 'Superhero / Action / Comedy' or 'Period Drama / Romance')

Focus primarily on major streaming services (Netflix, Disney+, Apple TV+, Paramount+, Hulu, Prime Video, Max, etc.), but include notable broadcast/cable premieres if they are high-profile (e.g., network reality competitions, major dramas). Only include shows that actually premiere new episodes, full seasons, or parts during that exact week—exclude trailers, announcements, or ongoing shows without new content starting.

Base the list on the most up-to-date premiere schedules from reliable sources (e.g., Deadline, Hollywood Reporter, Rotten Tomatoes, TVLine, Netflix Tudum, Disney+ announcements, Metacritic, Wikipedia TV pages). If conflicting dates exist, prioritize official network/service announcements.

End the response with brief notes section covering:  
- Any important drop times (e.g., time zone specifics like 6PM PT),  
- Release style (full binge drop vs. weekly episodes vs. split parts),  
- Availability caveats (e.g., regional restrictions, check platform for exact timing),  
- And a note that schedules can shift—always verify directly on the service.

If literally no major premieres in the week, state so briefly and suggest checking a broader range or popular ongoing shows.