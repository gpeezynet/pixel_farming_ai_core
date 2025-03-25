# AI Logic Flow – Drone-to-Pixel Mapping for FJRC Pixel Farming

This document outlines how the AI can take aerial imagery (drone or satellite), interpret the space, and create a 2'x2' pixel grid for assigning guilds.

---

## STEP 1: INPUT DATA ACQUISITION

**User Input** may include:
- Drone images or satellite images
- Approximate dimensions (length/width in feet or meters)
- Additional notes on existing trees, shade, slope

The AI cannot directly parse raw images (unless integrated with a vision model), so it relies on:
- User-provided dimension data
- Possibly a processed map overlay with coordinates

---

## STEP 2: DIMENSIONAL ANALYSIS

1. **Identify total area** in square feet (e.g., 20' x 30' = 600 sq ft).
2. **Divide** by 4 sq ft per pixel block (2'x2').
3. **Calculate** the potential number of pixels (600 ÷ 4 = 150 pixels).
4. **Note** any unplantable areas (structures, paths, existing trees).

---

## STEP 3: ZONE SEGMENTATION

If the yard has distinct zones:
- Full sun vs. partial shade
- Different soil types or slopes
- Water source proximity

Break the map into smaller segments. Each segment is assigned:
- A sun/soil classification
- A “max pixel capacity”

---

## STEP 4: PIXEL GRID CREATION

For each segment:
1. Determine how many 2'x2' blocks fit.
2. Number them in a consistent pattern (row by row, or spiral, etc.).
3. Optionally, note paths or walkways between pixel rows (1–2 ft buffer).

---

## STEP 5: GUILD ASSIGNMENT

Once the AI has a grid:
1. Evaluate **environment** for each pixel or segment (sun, soil, slope).
2. Pull from **Guild Selection Logic** (`guild_selection_logic.md`).
3. Assign each pixel a suitable guild code.

Optionally, the user can:
- Request specific patterns (letters, symbols, fractals)
- Force certain guilds in certain spots

---

## STEP 6: OUTPUT

### 1. Layout Map
A textual or coded representation of each row/column:
Each pixel references the chosen guild.

### 2. Summaries
- **Total pixel count** used
- **Guild distribution** (e.g., 10 blocks of A1, 5 blocks of A2, etc.)
- **Estimated bloom/harvest** timeline

### 3. Visual Overlays (Optional)
If integrated with a mapping tool, the AI can produce an overlay or coordinate grid referencing real-world lat/long or top-left offsets.

---

## STEP 7: USER CONFIRMATION & EDITS

- The AI presents the layout
- The user can reorder or swap guilds
- The AI finalizes a “Garden Plan” for printing or app-based guidance

---

## FUTURE ENHANCEMENTS

- Integrate with CV models to detect existing plant structures from drone imagery
- Dynamically adapt pixel size for irregular shapes
- 3D slope analysis for advanced water flow and terrace guilding
- Real-time progress tracking with weekly drone scans

---

## SUMMARY

This logic flow transforms an overhead yard dimension or image into a **pixel-based garden** with assigned guilds, respecting the environment, user goals, and aesthetic patterns. It merges the **Drone or map data** with the **FJRC Pixel Farming** approach—turning raw space into a living mosaic of food and ecology.
