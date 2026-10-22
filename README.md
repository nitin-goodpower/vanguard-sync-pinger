# vanguard-sync-pinger

Calls the Vanguard review app's scheduled-sync route every 30 minutes so new JazzHR
applicants are pulled in, indexed and screened without anyone running anything.

The app runs on a Vercel Hobby plan, whose own cron can only fire once a day, so this
workflow is the 30-minute trigger (and Vercel's daily cron is the backstop).

This repository is public because GitHub's free personal plan does not run scheduled
workflows in private repositories. Nothing sensitive is here: the route's secret is a
repository secret, the URL is a repository variable, and the workflow prints only the
HTTP status.

- `SYNC_URL` (repository variable): the app's `/api/cron/sync` URL.
- `CRON_SECRET` (repository secret): must equal the app's `CRON_SECRET` env var.

Run it by hand from the Actions tab ("Run workflow") to check it works.
