# Daily Briefing Config

**Time:** 7:00 AM ET (12:00 UTC)
**Recipient:** Lauren (Telegram chat 8633030167)
**Cron ID:** 6c96ccb8-5b28-4bde-b142-cb68808ca9e7

## Components
1. ☀️ Weather — Atlanta forecast for today (Open-Meteo)
2. 📅 Personal Calendar — Today's events from `primary` (lhaile7@gmail.com)
3. 💼 Work Calendar — Free/busy blocks before noon from `lauren.haile@superhuman.com`
4. ✅ Todoist — Tasks due today from #Home project only (project_id: 6CrfMRHRfR8HcwQF)

## Data Sources
- Weather: Open-Meteo API (Atlanta: 33.749, -84.388, fahrenheit, tz=America/New_York)
- Personal Calendar: `gog calendar events primary --account lhaile7@gmail.com --client personal`
- Work Calendar: `gog calendar events 'lauren.haile@superhuman.com' --account lhaile7@gmail.com --client personal` (free/busy only — no titles visible)
- Todoist: API v1 `/api/v1/tasks?project_id=6CrfMRHRfR8HcwQF` with $TODOIST_API_TOKEN

## Calendars Available
- primary: lhaile7@gmail.com (personal, full access)
- lauren.a.calvert@gmail.com (Lauren Calvert, owner)
- jhaile@gmail.com (Jeremy, reader)
- Family calendar
- ESPN calendar
- lauren.haile@superhuman.com (work, free/busy only)
