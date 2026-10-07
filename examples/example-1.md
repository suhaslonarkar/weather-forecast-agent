# Example 1 — Current Weather

> **Note:** All weather values in these examples are illustrative, to show format and behavior. A real run must use live retrieved data.

**User:** What is the weather in Pune today?

## Agent behavior

1. **Location:** Pune (stated).
2. **Time:** Today.
3. **Requirement:** General single-day question → standard format.
4. **Retrieve:** Fetch today's live forecast for Pune.
5. **Analyze:** Warm day, moderate humidity, a chance of evening showers.
6. **Respond:** Standard format with relevant fields only.

## Expected response

```text
🌤️ Weather — Pune

📅 Wednesday, 7 October 2026

🌡️ Temperature: 22–32°C (currently 29°C)
🌧️ Rain: 40% chance, mostly late afternoon and evening
💨 Wind: 10 km/h, light
💧 Humidity: 62%

Summary:
A warm, mostly cloudy day. Showers are fairly likely later in the day, but they should be brief and scattered rather than heavy.

Recommendation:
Carry a compact umbrella if you'll be out in the evening.
```

## What this demonstrates

- Standard output format
- Interpretation instead of raw numbers
- Rain probability translated into plain language ("fairly likely")
