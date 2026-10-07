# Weather Response Format Reference

Detailed formatting guidance for the Weather Forecast Skill. Load this when composing the final response.

## 1. Standard single-day / time-window format

```text
🌤️ Weather — <Location>

📅 <Date or time window>

🌡️ Temperature: <current or min–max>
🌧️ Rain: <probability / condition>
💨 Wind: <speed, direction if notable>
💧 Humidity: <value>

Summary:
<2–3 sentences interpreting the data>

Recommendation:
<one short practical tip>
```

Rules:

- Drop any line the user does not need or the data does not provide (e.g. omit Humidity for a pure rain question).
- Add "Feels like", "Visibility", or "Sunrise/Sunset" only when relevant to the question or notably unusual.
- Summary must interpret, not repeat the lines above.

## 2. Multi-day format

```text
🌤️ <Location> — <N>-Day Forecast

| Date | Condition | Temp | Rain |
|------|-----------|------|------|
| ...  | ...       | ...  | ...  |

Overall:
<1–2 sentence trend summary>

Best day:
<day and reason>

Rainiest day:
<day and reason, or "No significant rain expected">
```

Rules:

- One row per day. Keep cells short ("Partly cloudy", "24–31°C", "20%").
- Always include Overall, Best day, and Rainiest day.
- For 7 days, keep the same columns; do not add more.

## 3. Question-first (focused) format

When the user asks one specific thing, lead with a direct answer.

```text
<Direct answer in one sentence.>

<1–2 sentences of supporting detail: timing, probability, intensity.>

Recommendation: <short tip, if useful>
```

## 4. Simple current-weather format

No table. Two to three plain sentences:

```text
It's <temp> and <condition> in <Location> right now. <One notable detail>. <Optional tip.>
```

## 5. Interpretation guide

Use these as soft guides and adapt to local context. Always rely on the retrieved data, not on these numbers alone.

| Signal | Plain-language wording |
|--------|------------------------|
| Rain probability < 20% | Unlikely / small chance |
| 20–40% | Possible |
| 40–70% | Fairly likely |
| > 70% | Likely / expected |
| Thunderstorm in forecast | Mention lightning risk and possible disruption |
| Very high temperature or heat index | Note heat; suggest avoiding prolonged midday outdoor activity |
| Strong wind | Outdoor activity may be uncomfortable |
| Low visibility (fog, haze, heavy rain) | Allow extra travel time |
| Big day-night swing | Suggest layers |

## 6. Recommendation examples

- Rain: "Carry an umbrella or raincoat."
- Heat: "Consider avoiding prolonged outdoor activity around midday."
- Wind: "Outdoor activities may be uncomfortable."
- Travel: "Road travel may be affected if heavy rain is forecast."
- Pleasant: "Good conditions for outdoor plans."

Avoid medical advice and alarmist language.

## 7. When data is unavailable

```text
I couldn't retrieve current forecast data for <Location> right now, so I can't give reliable weather details. Please try again shortly, or I can search again if you'd like.
```

Never substitute estimated or typical values.
