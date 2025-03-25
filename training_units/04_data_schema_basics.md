# TRAINING UNIT 04 – Data Schema Basics for Pixel Farming

## Purpose of Data in Pixel Farming

Each pixel block is a living system. Logging its performance allows us to:
- Track growth, yield, bloom timing, pest issues
- Compare guild performance across environments
- Simulate outcomes based on climate or season
- Improve guild design over time
- Train AI models to optimize installations

---

## Core Pixel Log Fields (Structure Overview)

Each pixel should be assigned a unique ID and tracked using this structure:

```json
{
  "pixel_id": "A1-001",
  "guild_code": "A1",
  "location": {
    "latitude": 34.7304,
    "longitude": -86.5861,
    "zone": "7a"
  },
  "planted_on": "2025-03-29",
  "bloom_start": "2025-04-20",
  "harvest_dates": ["2025-06-15", "2025-07-01"],
  "yield": {
    "Tomato": "3.4 lbs",
    "Basil": "2 cups",
    "Chives": "50 grams"
  },
  "sunlight_hours_avg": 6.5,
  "watering_liters_per_week": 5.0,
  "pests_observed": ["aphids"],
  "notes": "Companion balance excellent. Tomato staked. No fungal issues."
}
