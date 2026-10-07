# Example 3 — Multi-Day Forecast

> **Note:** All weather values are illustrative. A real run must use live retrieved data.

**User:** Give me the weather forecast for Pune for the next 5 days.

## Agent behavior

1. **Location:** Pune (stated).
2. **Time:** Next 5 days starting today.
3. **Requirement:** Multi-day → table format.
4. **Retrieve:** Daily forecast for 5 days.
5. **Analyze:** Find the overall trend, the most pleasant day, and the rainiest day.
6. **Respond:** Table plus Overall, Best day, and Rainiest day.

## Expected response

```text
🌤️ Pune — 5-Day Forecast

| Date          | Condition     | Temp      | Rain |
|---------------|---------------|-----------|------|
| Wed, 7 Oct    | Cloudy        | 22–32°C   | 40%  |
| Thu, 8 Oct    | Light showers | 21–29°C   | 65%  |
| Fri, 9 Oct    | Partly cloudy | 21–31°C   | 25%  |
| Sat, 10 Oct   | Mostly sunny  | 20–33°C   | 10%  |
| Sun, 11 Oct   | Mostly sunny  | 20–34°C   | 10%  |

Overall:
Showery at the start of the period, then clearing and warming up toward the weekend.

Best day:
Saturday — sunny, dry, and comfortable in the morning, good for outdoor plans.

Rainiest day:
Thursday — rain is fairly likely through much of the day, so plan indoor alternatives.
```

## What this demonstrates

- Compact table with only four columns
- Trend summary, not just a list of numbers
- Best and rainiest day callouts that help with planning
