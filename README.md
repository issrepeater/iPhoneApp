# ISS Repeater — published support pages

**Live as of 2026-09-09.** Both URLs App Store Connect asks for now resolve,
without GitHub Pages being enabled.

| Field in App Store Connect | URL |
| --- | --- |
| **Privacy Policy URL** | `https://github.com/issrepeater/iPhoneApp/blob/main/privacy.md` |
| **Support URL** | `https://github.com/issrepeater/iPhoneApp` |

GitHub renders Markdown natively in the blob view, so both pages display
properly to anyone with the link, with no login and no build step. Apple's
requirement is that the URL resolves publicly and is relevant, which these do.
The only cost is GitHub's own chrome around the page.

## What is in the repo

`github.com/issrepeater/iPhoneApp`

- `README.md` — the support page. Shown automatically at the repo root, which is
  why the repo URL works as the Support URL.
- `privacy.md` — the privacy policy. Source of truth is `AppStore/privacy.md`
  in this Project; re-upload after any edit here.

## Fixed on 2026-09-09, after the first upload

The first published `privacy.md` had two broken links and one redundant block.
The version in this Project is corrected — **re-upload it over the published
one**:

1. `[← Back to support](index.html)` and `[support page](index.html)` both
   pointed at a file that does not exist in that repo. The footer link now
   points at `README.md`; the licence sentence now points at the app's own
   **Settings → Acknowledgements** screen, which is where those notices
   actually live.
2. The YAML front matter (`---` / `title: Privacy Policy` / `---`) was removed.
   Its only purpose is GitHub Pages, which is not enabled. See below if that
   changes.

## The licence notices are discharged in the app, not on the web

Worth knowing, because it decides how much the web pages matter: SatelliteKit's
MIT notice and the NOAA/BGS WMM attribution both ship **inside the binary**,
under Settings → Acknowledgements (added 2026-09-09). The support page carrying
them too is belt-and-braces, not the obligation. So the current README having no
licence section is not a gap.

If you want them on the web as well, the text to paste is in
`AppStore/index.html`'s footer, or ask for it as Markdown.

## `AppStore/index.html` — kept, not published

The richer support page (FAQ, how to read a window card, the settings glossary,
licence footer) is still in this Project. It is **not** what is published; the
repo's `README.md` is. Keep it if you later want a proper support site — it is
already written and needs only hosting. Delete it if the README is enough.

`AppStore/privacy.html` was deleted on 2026-09-09, superseded by `privacy.md`.

## If you later enable GitHub Pages

Only worth doing for a nicer URL and no GitHub chrome. Three things change:

1. **Add the front matter back** to `privacy.md`, or Jekyll will serve it as raw
   text rather than rendering it:
   ```
   ---
   title: Privacy Policy
   ---
   ```
   Files without front matter are copied verbatim, not converted — this is the
   single most common way a Markdown page on Pages ends up looking broken.
2. **Add an `index.html` or `index.md`**, or the site root 404s. `index.html` is
   already written and ready in this Project.
3. **Re-point the links.** `README.md` is not served by Pages; the footer link
   would need to become `./` or `index.html`, and the Privacy Policy URL becomes
   `https://issrepeater.github.io/iPhoneApp/privacy.html` — note `.html`, since
   Jekyll converts the `.md`.

Settings → Pages, Source = Deploy from a branch, Branch = `main`, folder =
`/ (root)`.

## Screenshots

`appstore-screenshots.sh` captures the booted Simulator and rescales one good
shot into each required pixel size. Drop the 13-inch iPad entry from its `SIZES`
array once iPad is removed from Supported Destinations (SETUP.md step 10) —
which has to happen before the capture session anyway, since the sky finder
ships broken in landscape.

Caption copy for each screenshot is in `AppStore/store-listing.md`.
