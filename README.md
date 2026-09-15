# b0g8.github.io

The website for b0g8's Android apps. Plain HTML and one stylesheet — no build step, no framework, and **no
external requests of any kind**: no web fonts, no CDN, no analytics. That is deliberate. The apps
this site is about claim not to track anyone, and a site that loads a font from someone else's
server while saying so is making the claim untrue in its own footer.

GitHub Pages serves it from the default branch at the repository root, so a push is a deploy.

## Pages

| Path | What it is |
|---|---|
| `index.html` | Landing page: who this is, and the two apps |
| `4k-video-editor/` | The app page — pitch, screenshots, what it does, where to report a bad export |
| `4k-video-editor/roadmap/` | What is being considered for that app, plus the vote |
| `retro-music-player/` | A holding page. It says there is nothing to install and no date, because there isn't |
| `roadmap/` | A forwarding page. This URL was public before roadmaps became per-app |
| `privacy/4k-video-editor.html` | That app's privacy policy |
| `privacy/retro-music-player.html` | That app's privacy policy |
| `404.html` | Served by Pages for anything else |

## Things to know before editing

- **Each app has its own policy, and they are not in the same situation.** The 4k Video Editor's is
  a **second copy**: the one Google Play points at is still the Weebly page
  (`wizefilmmaking.weebly.com/privacy-policy.html`), and both must say the same thing, because Play
  cross-checks the policy against the Data safety form. If one changes, change both — or move the
  Console to this URL and retire the Weebly copy. Retro Player's is the **only** copy, so it is the
  URL its Console listing should point at when that listing exists.
- **The two policies describe different apps and are meant to differ.** The editor has Crashlytics;
  the player has no crash reporting at all. The editor asks for no media permission; the player asks
  to read audio files and explains why. Do not "harmonise" them.
- **The roadmap is per app.** Each app owns its own, under the app's directory. There is no global
  one, and no Roadmap entry in the nav: the nav is the apps.
- **The vote is a form that opens the visitor's mail app**, with their choice filled in. It needs no
  backend and works today. When a real form exists (Tally, Google Forms, anything that collects and
  counts), replace the submit handler — the spot is marked INTERIM in
  `4k-video-editor/roadmap/index.html`. Link out rather than embedding: an `<iframe>` would be the
  first external request this site makes.
- **Nothing on this site asks for money.** In-app donations are deliberately not mentioned anywhere
  except the privacy policy, which has to describe them because Play cross-checks that document
  against the data safety form.
- **The roadmap must stay true.** Its whole value is that "being considered" really does mean
  considered, and that "next up" is not marketing. An item that ships moves to Shipped; an item
  that is abandoned comes off the page rather than sitting at "next up" for a year.
- **Screenshots** are downscaled from `docs/release/screenshots/` in the app repo (600px wide,
  JPEG). Re-export them from there rather than editing the copies here.
- **There is no brand name.** "Photocraft" was the header, footer and `<title>` of every page until
  2026-09-15, when the owner removed it: everything already lives under the `b0g8` handle and a
  third name — beside `Photocraft` in the repo `LICENSE` and `WIZE FILM MAKING` on the Play listing
  — was one more than anyone needed. The header's left slot is now `b0g8`, which is the site's
  address and its home link; the copyright line says the same.
- **The Donate button goes to `paypal.me/RusBogdan`** and sits in the top row of every page. It is
  safe under Play's Payments policy for one specific reason, and the reason has to stay true: a
  contribution where 100% goes to the developer and that **grants no digital content or service**
  is a peer-to-peer payment, not an in-app purchase, so Play Billing is not required for it. The
  day a donation unlocks anything, this link becomes steering around Play Billing on a listing with
  a million downloads. **Nothing in the app links to PayPal directly**, and nothing should.

## Working on it locally

```
python3 -m http.server 8731
```

Then open <http://localhost:8731/>. Root-relative paths (`/assets/...`) resolve correctly that way,
which is why the pages use them.
