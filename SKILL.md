---
name: weather-forecast
description: Answers weather questions for a named place or the user's current location, such as today's weather, rain chances, tonight, this weekend, or a 3-7 day outlook. Use whenever the user asks about weather, temperature, rain, wind, or forecasts. Retrieves live forecast data, interprets it, and gives a concise answer with a practical recommendation. Never invents weather values.
---

# Weather Forecast Skill

Turn a natural-language weather question into a short, accurate, useful answer.

## Workflow

1. **Identify location**
2. **Identify date/time**
3. **Determine forecast requirement**
4. **Retrieve weather data**
5. **Analyze forecast**
6. **Generate concise response**
7. **Add practical recommendation**

## 1. Identify location

- Use the place the user names ("Pune", "Bangalore").
- If the user says "near me" or "here", use the environment's location capability if one exists. If none exists, ask for the city.
- If no location is given, ask: "Which city or area should I check?"
- Never guess or invent a location.

## 2. Identify date/time

Resolve relative phrases against **today's actual date** (from the environment or system context).

| User says | Forecast period |
|-----------|-----------------|
| now / current | Current conditions |
| today | Rest of today |
| tonight | Today ~8 PM to ~6 AM |
| this evening | Today ~5 PM to ~9 PM |
| tomorrow | Tomorrow, full day |
| tomorrow evening | Tomorrow ~5 PM to ~9 PM |
| this weekend | Upcoming Saturday and Sunday |
| next 3 / 5 / 7 days | That many days starting today |

If the request is genuinely ambiguous (e.g. "next weekend" near a weekend, or no time given for a rain question), ask **one** short clarifying question. If no time is given for a general weather question, assume **today**, and say so.

## 3. Determine forecast requirement

Choose the response type:

- **Simple current question** → short answer, no table.
- **Single-day or time-window question** → standard format.
- **Specific question** (rain? wind? hot?) → answer that question first, then add only relevant context.
- **Multi-day request (2+ days)** → multi-day table format.

## 4. Retrieve weather data

- Use web search, a weather tool, or any live data source the platform provides.
- Prefer live or recent data for current, today, and tomorrow requests.
- Note the source or retrieval time when the platform makes it available.
- **If no live data can be retrieved, say so plainly** and offer to try again. Do not estimate, recall "typical" values, or fill gaps.
- If only some fields are available, use those and omit the rest silently.

## 5. Analyze forecast

Interpret; do not just repeat numbers. Look for:

- Rain risk and timing
- Extreme heat or cold
- Strong winds
- Thunderstorms
- Poor visibility
- Large temperature swings

Mention a risk **only if the retrieved data supports it**. Do not exaggerate. Use hedged language for uncertain forecasts ("fairly likely", "a small chance").

## 6. Generate response

Follow the templates in [references/weather-response-format.md](references/weather-response-format.md). Show only the fields relevant to the question. Keep it short.

## 7. Practical recommendation

Add one brief, relevant tip when useful (umbrella, avoid midday sun, expect windy conditions, allow extra road time in heavy rain). Skip it when there is nothing meaningful to say. Do not give medical advice.

## Rules

- Never fabricate temperatures, probabilities, or conditions.
- Answer the user's actual question first.
- Do not build a table for simple current-weather questions.
- Use °C for India and most countries, °F for the US, unless the user asks otherwise.
- Ask at most one clarifying question.
