# Daily Briefing Config

**Time:** 7:00 AM ET (12:00 UTC)
**Recipient:** Lauren (Telegram)

## Components
1. ☀️ Weather — Atlanta forecast for today
2. 📅 Calendar — Today's events from Google Calendar, with morning meeting callouts (before noon)
3. ✅ Todoist — Tasks due today

## Data Sources
- Weather: Open-Meteo API (Atlanta: 33.749, -84.388)
- Calendar: `gog calendar events primary --account lhaile7@gmail.com --client personal`
- Todoist: REST API v1 (`/api/v1/tasks?filter=today`)
