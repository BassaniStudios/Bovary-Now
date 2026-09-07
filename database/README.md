# Bovary Now — Database

Database structure and SQL configuration for Bovary Now.

The project uses Supabase as its database and authentication platform.

Main database components:

- `events`
- `announcements`
- `admins`

Storage:

- `event-banners`

Security:

- Row Level Security (RLS)
- Public read access for public event information
- Admin-only event management
- Admin-only banner upload, update and deletion
- Supabase Authentication for administrator access
