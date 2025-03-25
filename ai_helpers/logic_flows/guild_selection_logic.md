# AI Logic Flow – Guild Selection for Pixel Farming

This file outlines the decision process the AI should follow when generating a new plant guild for a 2'x2' Pixel Block. The goal is to ensure ecological compatibility, diverse function, and balanced design.

---

## STEP 1: INTERPRET THE USER REQUEST

Extract from prompt:
- Desired **environment** (sunlight, soil type, climate zone)
- Intended **purpose** (culinary, pollination, visual, pest control, etc.)
- Any **constraints** (e.g., no tall plants, low water use, specific plant preferences)

If missing, ask follow-up questions.

---

## STEP 2: SELECT ANCHOR CROP

Choose 1 plant as the **anchor crop** (the main yield source or visual center).

Consider:
- Does it match sun, soil, and zone?
- Will it grow to full size in a 2'x2' bed?
- Is it harvestable, useful, or symbolic?

---

## STEP 3: FILTER COMPANIONS

Use the plant catalog to filter **compatible companions**:
- No root competition (mix shallow, mid, and deep)
- No known antagonism
- Prefer complementary functions

Aim for:
- 1 pollinator draw
- 1 pest repellent or trap crop
- 1 flavor or nutrient enhancer
- 1 ground cover (optional)

---

## STEP 4: ASSIGN POSITIONS

Default layout (if user doesn't specify):

| Position   | Role               |
|------------|--------------------|
| Center     | Anchor Crop        |
| Corner 1   | Repellent          |
| Corner 2   | Pollinator/Visual  |
| Corner 3   | Flavor/Nutrient    |
| Corner 4   | Optional cover crop or empty space |

Height stacking:
- Tall center
- Mid-height companions
- Low ground covers

---

## STEP 5: VALIDATE ENVIRONMENTAL MATCH

Check all selected plants:
- Sun exposure
- Soil preference
- Climate zone compatibility
- Similar water needs

If mismatch: auto-adjust or prompt for user input.

---

## STEP 6: BUILD JSON OUTPUT

Generate `.json` file using the structure defined in `guild_schema.json`.  
Include:
- `guild_code` (auto-generated or sequential)
- Plant array with position, type, and height
- `environment`, `soil_depth`, `bloom_window`, `function`, and `harvest` fields

---

## STEP 7: EXPLAIN CHOICES (OPTIONAL)

After outputting the JSON, summarize:
- Why these plants work together
- What benefits this guild provides
- When to plant, bloom, and harvest

---

## EXAMPLE REQUEST → DECISION FLOW

**Prompt:**  
"Build a drought-tolerant culinary guild for full sun in zone 9b."

**Flow:**  
- Anchor crop: Pepper (culinary, heat-tolerant)
- Companion: Basil (low water, flavor enhancer)
- Companion: Oregano (ground cover, pest repellent)
- Companion: Borage (pollinator, visual)
- Layout based on height/root compatibility

---

## ENDPOINTS

This logic should produce:
- A valid, balanced, diverse guild
- JSON output for machine use
- Plain-text summary for human use
- Optional layout map or build plan

