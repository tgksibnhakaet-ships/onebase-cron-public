# OneBase Public Cron Jobs

This is a **public** GitHub repository used only as a free cron trigger via GitHub Actions.

Public repos get **unlimited** GitHub Actions minutes (vs. 2,000/month for private).

## What this does
- Every 5 minutes: triggers bridge queue poller + key migrator
- Daily at 18:00 UTC: triggers OneBase daily summary
- Weekly Sunday 02:00 UTC: pings Supabase to keep it active (prevents 1-week inactivity pause)

## Secrets
Configure in `Settings → Secrets and variables → Actions`:
- `BRIDGE_URL` — public URL of the Bridge (CF Worker)
- `CRON_TOKEN` — bridge auth token for cron endpoint
- `SUPABASE_URL` — your Supabase project URL
- `SUPABASE_ANON_KEY` — public anon key (safe to store here)

No source code or sensitive credentials are stored in this repo.
