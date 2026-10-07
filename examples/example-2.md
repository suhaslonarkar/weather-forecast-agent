# Example 2 — Rain Prediction

> **Note:** All weather values are illustrative. A real run must use live retrieved data.

**User:** Will it rain in Mumbai tomorrow evening?

## Agent behavior

1. **Location:** Mumbai (stated).
2. **Time:** Tomorrow, ~5 PM to ~9 PM.
3. **Requirement:** Specific rain question → answer first, keep it short.
4. **Retrieve:** Hourly rain forecast for tomorrow evening.
5. **Analyze:** Rain probability and timing within the window; check for thunderstorms and wind.
6. **Respond:** Question-first format. No full weather report.

## Expected response

```text
Yes, rain looks likely in Mumbai tomorrow evening.

The chance of rain rises to about 75% between 6 and 8 PM, with moderate showers expected and a possible rumble of thunder. It should ease after about 9 PM.

Recommendation: Carry an umbrella or raincoat, and allow extra time if you're travelling by road around 6–8 PM.
```

## Why it is short

The user asked one question about rain and timing. The agent leads with the answer, adds timing and intensity, and leaves out temperature, humidity, and other fields.

## If the user had asked "Will it rain in Mumbai?"

The time is missing, so the agent would ask once: *"Do you mean today, tonight, or tomorrow?"*
