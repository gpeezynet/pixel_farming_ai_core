# TRAINING UNIT 02 – Guild Logic & Structure

## What Is a Guild?

A guild is a small group of plants that support each other. In Pixel Farming, each 2'x2' pixel block contains 3–5 plants carefully selected for ecological harmony, yield, and beauty.

---

## Core Plant Roles

| Role               | Purpose                                      |
|--------------------|----------------------------------------------|
| Anchor Crop        | Main yield crop (tomato, pepper, lettuce)    |
| Repellent          | Protects from pests (marigold, chive, garlic)|
| Pollinator Draw    | Attracts bees (borage, chamomile, calendula) |
| Flavor Booster     | Improves taste/health of neighbors (basil)   |
| Soil Builder       | Adds N or breaks compaction (radish, legumes)|
| Ground Cover       | Prevents weeds + conserves water (thyme)     |
| Medicinal / Bonus  | Useful herbs, tea plants, natural remedies   |

---

## Guild Construction Logic

- One anchor crop
- One or two functional companions (repellent, builder, etc.)
- One pollinator or flower
- Optional bonus crop or empty corner

Balance:
- **Root Depth**: Avoid stacking all shallow or all deep
- **Height**: Center plant taller, corners low/mid
- **Sunlight**: Match to environment request (full sun, partial, dry)

---

## Example Guild Format

```json
{
  "guild_code": "A1",
  "name": "Kitchen Block",
  "plants": [
    { "name": "Tomato", "position": "center", "type": "fruit", "height": "tall" },
    { "name": "Basil", "position": "corner_1", "type": "herb", "height": "mid" },
    { "name": "Chives", "position": "corner_2", "type": "herb", "height": "low" },
    { "name": "Marigold", "position": "corner_3", "type": "flower", "height": "mid" }
  ],
  "environment": "Full Sun",
  "soil_depth": "8in",
  "bloom_window": ["June", "August"],
  "harvest": ["Tomato", "Basil", "Chives"],
  "function": ["culinary", "pollinator", "pest deterrent"]
}
