### DOCUMENTATION (v1.6.1)
- AUTHORS: Scott M.
- GOAL: Generate a scientifically accurate, 180-degree zenith view of the night sky (straight up) reflecting exact star, planet, and Milky Way alignment for a given location and time.
- CHANGELOG: 
  - v1.6.1: Added input validation, explicit IF/ELSE label handling, resolved 14mm vs 180-degree optic conflicts, updated target engine models.
  - v1.6.0: Optimized for prompt-to-image processors; moved technical metadata to top; reinforced Scott M. authorship.
- TARGET ENGINES: Midjourney, Flux, Imagen, or similar top-tier diffusion models.

---

### INPUT VALIDATION & EDGE CASES
Before generating output, validate [LOCATION] and [TIME/DATE]:
- Missing or Nonsense Inputs: If [LOCATION] or [TIME/DATE] is missing, invalid, or gibberish, prompt the user for clarification. If forced to execute, default to Mauna Kea, Hawaii (19.82° N, 155.46° W) at UTC 00:00.
- Labels Input: Must be explicitly 'Yes' or 'No'. Default to 'No' if unspecified.

---

### USER INPUTS
1. [LOCATION]: (e.g., Mauna Kea, Hawaii or 19.82° N, 155.46° W)
2. [TIME/DATE]: (e.g., August 12, 2026, 2:00 AM local time)
3. [LABELS]: (Yes/No)

---

### GENERATED PROMPT OUTPUT

#### POSITIVE PROMPT
"A high-fidelity, true 180-degree circular fisheye zenith photograph of the night sky, looking 90 degrees straight up toward the astronomical zenith from [LOCATION] on [TIME/DATE]. 

Full celestial hemisphere field of view centered on the zenith. Bortle Class 1 pristine dark-sky quality. Absolute 0% ground, zero trees, zero horizon, and zero landmass visible. Pinpoint sharp star field, scientifically accurate planetary alignments, and realistic Milky Way core orientation mapped precisely to the specified date, time, and coordinates.

[IF LABELS=YES: Include thin, crisp, 1px white constellation overlay lines and minimalist sans-serif text labels for major stars, planets, and Messier objects with 70% opacity.]
[IF LABELS=NO: Pure clean astrophotography with zero overlaid lines, zero text, zero visual overlays, and no graphic elements.]

Photographic parameters: Astrophotography style, 25-second exposure, ISO 3200, pinpoint star optics, true optical black background, zero digital noise, zero star trailing, true astronomical fidelity."

#### NEGATIVE PROMPT
Ground, trees, terrain, mountains, horizon, landscape, buildings, clouds, atmospheric haze, satellite trails, aircraft, light pollution, city glow, oversaturated purple or magenta tint, digital painting style, illustration artifacts, fake lens flare, glare, watermarks, sun, daylight, blurred stars, motion blur.