# TOOLS.md - Local Notes

## Google Workspace
- **Personal account:** lhaile7@gmail.com (client: personal)
  - Calendar, Gmail (read+write), Drive, Sheets, Docs (read)
- **Work account:** lauren.haile@superhuman.com (not fully authenticated yet)
  - Calendar free/busy only via personal account subscription
- **gog CLI note:** Must use `--client personal` with `--account lhaile7@gmail.com`

## Calendars
| Calendar ID | Name | Access |
|---|---|---|
| primary (lhaile7@gmail.com) | Lauren's personal | Full |
| lauren.a.calvert@gmail.com | Lauren Calvert | Owner |
| jhaile@gmail.com | Jeremy | Reader |
| family09255384421674614946@group.calendar.google.com | Family | Owner |
| lauren.haile@superhuman.com | Work (Superhuman) | Free/busy only |
| ESPN calendar | ESPN | Owner |

## Todoist
- **API:** v1 (`https://api.todoist.com/api/v1/`)
- **Auth:** Bearer token in `$TODOIST_API_TOKEN` env var
- **Key project IDs:**
  - Home: `6CrfMRHRfR8HcwQF` ← used in daily briefing
  - Work: `6CrfVjhjMW378f64`
  - Inbox: `6CrfVjhjM9WRMg53`
  - Restaurants: `6CrfMRHRmRmHmrv2`
  - Favorite Restaurants: `6CrfMRHRpcmjhVWW`
  - Activities: `6CrfMRHRmG8RHc7w`
  - Porsche 964: `6CrfMRHRmrg66F4j`
  - Contractor/Home projects: `6CrfMRHRhgvppmX2`
  - Makery projects: `6CrfMRHRqr38mFw4`

## Cron Jobs
| Name | ID | Schedule | What |
|---|---|---|---|
| daily-briefing | 6c96ccb8-5b28-4bde-b142-cb68808ca9e7 | 0 12 * * * UTC (7am ET) | Weather + calendar + Todoist |

## Key Contacts
- **Jeremy Haile** (husband): jhaile@gmail.com, jeremy@sideqik.com
