# SAMS status (uptime check)

This small **public** repository only checks, every 5 minutes, that SAMS answers from outside:
the API (and its database), the website and the demo. It contains no SAMS code, only the public addresses.

When SAMS can't be reached (3 tries, 20 seconds apart), it opens an issue **"SAMS is down"**: GitHub e-mails you and
notifies the GitHub mobile app. When SAMS answers again, the issue gets a comment with how long it was down and closes.

Set-up (5 minutes):
1. GitHub → **New repository** → name `sams-status`, **Public**, create.
2. Upload this folder's contents (including `.github/workflows/uptime.yml`).
3. If your addresses differ, edit `API_HEALTH`, `WEBSITE` and `DEMO` at the top of `uptime.yml`.
4. **Actions** tab → enable workflows → **Uptime check** → **Run workflow**: all three lines must be ✅ in the run summary.
5. Settings → Notifications (your GitHub account): e-mail on for "Issues". Install the GitHub mobile app for push alerts.

GitHub pauses scheduled workflows in a repository with no commits for 60 days; it e-mails you before that. Press
"Enable workflow" (or commit any small change) to keep it running.
