# b0g8.github.io

The Photocraft website. Plain HTML and one stylesheet — no build step, no framework, and **no
external requests of any kind**: no web fonts, no CDN, no analytics. That is deliberate. The apps
this site is about claim not to track anyone, and a site that loads a font from someone else's
server while saying so is making the claim untrue in its own footer.

GitHub Pages serves it from the default branch at the repository root, so a push is a deploy.

## Pages

| Path | What it is |
|---|---|
| `index.html` | Landing page: who this is, and the two apps |
| `4k-video-editor/` | The app page — pitch, screenshots, what it does, where to report a bad export |
| `retro-music-player/` | A holding page. It says there is nothing to install and no date, because there isn't |
| `roadmap/` | Shipped / being built next / being considered, plus the vote |
| `privacy/4k-video-editor.html` | The privacy policy |
| `404.html` | Served by Pages for anything else |

## Things to know before editing

- **The privacy policy here is a second copy.** The one Google Play points at is still the Weebly
  page (`wizefilmmaking.weebly.com/privacy-policy.html`), and both must say the same thing, because
  Play cross-checks the policy against the Data safety form. If one changes, change both — or move
  the Console to this URL and retire the Weebly copy.
- **The vote is a `mailto:` link.** It needs no backend and it works today. When a real form exists
  (Tally, Google Forms, anything that collects and counts), swap it in — there is a comment in
  `roadmap/index.html` marking the spot.
- **The roadmap must stay true.** Its whole value is that "being considered" really does mean
  considered, and that "next up" is not marketing. An item that ships moves to Shipped; an item
  that is abandoned comes off the page rather than sitting at "next up" for a year.
- **Screenshots** are downscaled from `docs/release/screenshots/` in the app repo (600px wide,
  JPEG). Re-export them from there rather than editing the copies here.
- **The brand name is "Photocraft"**, which appears in the header, the footer and the `<title>` of
  every page. Google Play still publishes the app under the legacy developer name; if the two are
  ever reconciled, this is the place to change.

## Working on it locally

```
python3 -m http.server 8731
```

Then open <http://localhost:8731/>. Root-relative paths (`/assets/...`) resolve correctly that way,
which is why the pages use them.
