### Celestial Vision: Zenith Precision (v1.4)
### GOAL
To generate a scientifically-grounded, 180-degree zenith visualization of the night sky, accurately reflecting the celestial hemisphere of a specific location and time, with optional astronomical labeling.

### INPUT DATA & LOGIC GATE (USER ACTION REQUIRED)
1. [LOCATION]: Name, Coordinates, or Google Maps URL.
2. [TIME/DATE]: Specific date and time (e.g., Winter Solstice, 11:00 PM).
3. [LABELS]: (Yes/No) Indicate if constellations and major stars should be annotated.

**CONDITIONAL ACTION:**
- IF ALL inputs are provided: Proceed to generate the visualization.
- IF ANY are missing: DO NOT generate. Instead, ask: 
  *"To calibrate the Zenith view, please provide the missing [Location], [Time/Date], or [Label Preference]."*

### AI Engine Performance Ranking (Early 2026)
1. Midjourney v7.0 (Best for long-exposure textures)
2. Grok / Flux-based (Best for pinpoint star sharpness and text-in-image labeling)
3. Gemini 3 Pro [Nano Banana Pro] (Best for location/temporal reasoning and metadata)
4. Flux 2 Max (Best for raw astronomical fidelity)

### CORE SPECIFICATIONS
- VIEWPORT: Absolute 90-degree Zenith view (directly overhead).
- OBSTRUCTIONS: Zero terrestrial elements (No horizon, trees, or buildings).
- SKY QUALITY: Bortle Class 1 (Pristine Dark-Sky site). 100% transparency.
- TEMPORAL/LATITUDE ACCURACY: Render star positions, planetary alignment, and Milky Way orientation based strictly on [LOCATION] and [TIME/DATE].
- ANNOTATION LAYER (If LABELS=Yes): 
  - Draw thin, elegant constellation lines.
  - Add minimalist sans-serif text labels for major stars (e.g., Vega, Sirius) and Deep Sky Objects (e.g., M31, Pleiades).
  - Ensure labels do not clutter the frame.
- PHOTOGRAPHIC OPTICS: 14mm f/1.8 wide-angle lens mimicry. Sharp focus to infinity.
- SENSOR DATA: ISO 3200, 25-second exposure. Perfectly round pinpoint stars (tracked mount).

### NEGATIVE PROMPT
Ground, trees, mountains, horizon, clouds, satellites, airplanes, light domes, neon purple saturation, digital art style, sparkles, watermarks, star trailing, motion blur, sun, daylight.

---
### CHANGELOG (v1.4)
- Added [LABELS] toggle for optional constellation and star mapping.
- Refined annotation style to "minimalist sans-serif" to maintain photorealistic feel.
- Reinforced mandatory logic gate for Location/Time/Labeling status.
