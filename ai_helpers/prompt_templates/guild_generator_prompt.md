# Guild Generator Prompt Template – FJRC Pixel Farming

This file defines how the AI should generate a new companion planting guild for a 2’x2’ Pixel Block. The response should follow a clear structure, output usable data, and teach the user *why* the guild works.

---

## USER PROMPT EXAMPLE

"Create a companion guild for a pixel block in full sun with dry soil. The goal is to attract pollinators and provide fresh herbs for a household in zone 8a."

---

## OUTPUT FORMAT (3-Part Response)

### 1. Guild Summary

**Guild Name:** [Descriptive name]  
**Environment:** [Sun, soil, region]  
**Purpose:** [Yield + ecological function]  
**Zone:** [USDA hardiness zone]

---

### 2. Plant Table

| Plant      | Role              | Root Depth | Height |
|------------|-------------------|------------|--------|
| Tomato     | Anchor crop        | Deep       | Tall   |
| Basil      | Flavor booster     | Shallow    | Mid    |
| Marigold   | Pest deterrent     | Shallow    | Mid    |

Roles may include:
- Anchor crop
- Repellent
- Pollinator draw
- Ground cover
- Shade provider
- Soil builder
- Trap crop
- Flavor booster

---

### 3. JSON Output

```json
{
  "guild_code": "AUTO-GEN",
  "name": "Pollinator Power Block",
  "plants": [
    {
      "name": "Tomato",
      "type": "fruit",
      "position": "center",
      "height": "tall"
    },
    {
      "name": "Basil",
      "type": "herb",
      "position": "corner_1",
      "height": "mid"
    },
    {
      "name": "Marigold",
      "type": "flower",
      "position": "corner_2",
      "height": "mid"
    }
  ],
  "environment": "Full Sun",
  "soil_depth": "8in",
  "bloom_window": ["June", "August"],
  "harvest": ["Tomato", "Basil"],
  "function": ["culinary", "pest deterrent", "pollinator"]
}
