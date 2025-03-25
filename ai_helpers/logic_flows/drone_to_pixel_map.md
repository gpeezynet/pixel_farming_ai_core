# AI Logic Flow – Drone Mapping to Pixel Layout Plan

This file defines how the GPT should convert a visual space (from drone imagery or dimensions) into a functional grid of 2'x2' pixel blocks, and assign guilds across the layout based on function, environment, and bloom strategy.

---

## STEP 1: GET THE SPACE DIMENSIONS

If a drone image is not available, ask for:
- Total area dimensions (e.g., 10’ x 20’)
- General orientation (e.g., south-facing, shaded left side)
- Notable obstacles (e.g., tree, shed, walkway)
- Soil condition and sun exposure per section if known

---

## STEP 2: GRID THE SPACE

- Divide the space into 2’x2’ units
- Label each as a **pixel coordinate** (e.g., A1, A2, B1, etc.)
- Determine available pixel count and layout structure
  - Example: 10x20 space = 5 pixels wide by 10 pixels long = 50 total pixels

Store grid as a 2D array with placeholders for guild assignment.

---

## STEP 3: DEFINE ZONE CONDITIONS

If drone data is available (optional):
- Use elevation, slope, or light detection (via LiDAR or sunlight modeling)
- Segment layout by condition:
  - Full sun
  - Partial shade
  - Moist vs dry areas

Assign **zone tags** to each pixel:  
`A1: full_sun`, `B3: partial_shade`, etc.

---

## STEP 4: ASSIGN GUILDS

For each pixel:
- Match to a compatible guild from the library based on:
  - Environmental tag (sun, soil)
  - Visual diversity
  - Crop function (pollinator, yield, visual, healing, etc.)
- Avoid repeating the same guild in adjacent blocks if diversity is prioritized

Optionally follow design themes:
- Mandala
- Glyph (words, shapes)
- Fractal symmetry
- Functional zoning (center = yield, edges = pollinators)

---

## STEP 5: OUTPUT LAYOUT PLAN

Return:
- Grid visualization (markdown table or SVG-ready array)
- Guild assignment map:
  - A1 → A1_Kitchen_Block
  - A2 → A2_Salad_Block
- Optional bloom forecast timeline (color-coded)

Example Output:

|     |  A  |  B  |  C  |  D  |
|-----|-----|-----|-----|-----|
|  1  | A1  | A2  | A3  | A4  |
|  2  | A2  | A3  | A4  | A1  |
|  3  | A3  | A1  | A2  | A3  |

---

## STEP 6: OFFER NEXT ACTION

After layout, ask user:
- Would you like to generate a printable planting plan?
- Want to simulate bloom color over time?
- Ready to create a care guide or resource estimate?

---

## END GOAL

The AI should be able to:
- Convert a user’s yard dimensions or drone photo into a grid
- Assign meaningful guilds across the layout
- Provide install plans, seasonal visuals, and care schedules
