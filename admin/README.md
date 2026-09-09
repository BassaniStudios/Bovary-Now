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
