# Spencer's family calendar

Static page served by the Cloudflare Worker `spencer-calendar-dev`.

- `public/index.html` is the whole site. Calendar data lives in the lists near the top of its script
  (`NIGHTS`, `EVENTS`, `SCHOOL_ROUTINE`); change `UPDATED` whenever the calendar is edited.
- `public/_headers` keeps the page out of search engines.
- Pushing to `main` redeploys the site once the Worker is connected to this repo in Cloudflare.

## Nightly Slack updates

A scheduled Claude task runs at midnight (Sydney). It reads new messages in Slack #general
(channel C0CJXJW47QD), applies calendar changes to `public/index.html`, and pushes.
`state/last-slack-ts.txt` holds the timestamp of the last Slack message already applied.
