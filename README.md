# vanguard-sync-pinger

Calls the Vanguard review app's scheduled-sync route every 30 minutes so new JazzHR
applicants are pulled in, indexed and screened without anyone running anything.

The app lives on a Vercel Hobby plan, whose own cron can only fire once a day, so this
workflow is the 30-minute trigger (and Vercel's daily cron is the backstop).

- `SYNC_URL` (repository variable): the app's `/api/cron/sync` URL.
- `CRON_SECRET` (repository secret): must equal the app's `CRON_SECRET` env var.

Run it by hand from the Actions tab ("Run workflow") to check it works.
