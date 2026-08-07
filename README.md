# Shubhayan Sengupta — mentoring site

Static site. No build step, no dependencies. Put every file in the root of a GitHub
repo, import it into Vercel with Framework Preset **Other** and empty build settings.

## Files

| File | What it is |
|---|---|
| `index.html` | Landing page — hero, about, course grid with the age filter, testimonials |
| `batches.html` | Class formats, weekly timings table, fees, enrolment notes |
| `videos.html` | YouTube video grid, driven by a list at the bottom of the file |
| `contact.html` | Contact details plus the Google Form embed |
| `styles.css` | All styling for all four pages — change a colour here and it changes everywhere |
| `site.js` | Sticky header, mobile menu, scroll reveal, footer year |

## Before you publish — edit these

**1. `contact.html`** — near the bottom:
```js
var GOOGLE_FORM_EMBED_URL = '';
```
In Google Forms: **Send → `<>` (embed) → copy the `src="..."` value** and paste it
between the quotes. Until then the page shows a WhatsApp fallback panel instead.

**2. `videos.html`** — near the bottom:
```js
var CHANNEL_URL = 'https://www.youtube.com/';
var VIDEOS = [ ... ];
```
Set your channel URL. For each video, uncomment a line and paste the video id — the part
after `v=` in the YouTube URL. Thumbnails load automatically. An empty list shows a
"coming soon" panel, so the page is safe to publish before the channel is ready.

**3. `batches.html`** — three places, each marked with an `EDIT:` comment:
- fee lines in the three format cards (currently "Shared on request")
- the timings table rows — days, times, courses, and open / batch full status
- the four "Good to know" policy cards

**4. `index.html`** — the three testimonials are placeholders. Replace them with real
feedback, with the person's permission, before going live.

## Adding a page later

Copy `contact.html`, delete everything between `<section class="page-head">` and the
`<footer>`, write your content, and add a link to the `.nav`, `.mobile-nav` and
`.footer-links` lists on **all** pages. There's no template engine here, so navigation
is duplicated per page by design — it's five small edits.
