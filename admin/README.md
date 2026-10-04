# Bovary Now — Admin Panel

Private admin UI for **Bovary Club Society (Legacy)** and **Fenrir Yakuza (FiveM)**.

## Sections

| Menu | Supabase tables |
|------|-----------------|
| Dashboard / Events / Announcements | `events`, `announcements` |
| **Fenrir Events** | `fenrir_events` |
| **Fenrir Announcements** | `fenrir_announcements` |

## Before first use (FiveM)

1. Run the Fenrir SQL from `database/supabase_schema.sql` (or the block in the project docs) in Supabase SQL Editor.
2. Confirm tables `fenrir_events` and `fenrir_announcements` exist.
3. Open this `index.html` (or your hosted admin URL), login as admin.
4. Use **Fenrir Events** / **Fenrir Announcements** to publish content for the Android app **FiveM** tab.

## Ending a session (Last Meet + banner)

Use **END** on an active Fenrir event (or set status to `ended` in the form).

- Only `status` is updated to `ended`.
- **`image_url` is never cleared** — required for the app Last Meet banner.

## Local open

Open `admin/index.html` in a browser (or serve the folder). Configure Supabase URL + anon key in Settings as before.

## Activity buttons (PING + App Pulse)

Two buttons generate database activity without changing what members see in the app:

| Button | Where | What it does |
|--------|--------|----------------|
| **PING · /ping** | Dashboard + Settings | Writes a heartbeat to table `keepalive` (source `admin-ping`) |
| **APP PULSE** | Dashboard + Settings | Runs the same SELECTs the member app would on open (events, announcements, fenrir_*) then a silent heartbeat (source `app-pulse`). **No visible UI change in the app.** |

### Setup

1. Run the **KEEP ALIVE** block at the end of `database/supabase_schema.sql` in the Supabase SQL Editor.
2. Open the admin panel, login, click **PING** or **APP PULSE**.

