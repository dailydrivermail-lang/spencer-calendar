# Spencer's family calendar

Static page served by the Cloudflare Worker `spencer-calendar-dev`.

- `public/index.html` is the whole site. Calendar data lives in the lists near the top of its script
  (`NIGHTS`, `EVENTS`, `SCHOOL_ROUTINE`); change `UPDATED` whenever the calendar is edited.
- `public/_headers` keeps the page out of search engines.
- Pushing to `main` redeploys the site once the Worker is connected to this repo in Cloudflare.
