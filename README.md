# saffronstreet-site

Public site for **Saffron Street: Merge & Serve** (TonTech). Static GitHub Pages project site:
https://tontechco.github.io/saffronstreet-site/

- `/` landing, `/privacy/`, `/terms/`, `/support/`
- `/i/<CODE>`: invite page. Project Pages cannot route, so GitHub serves `404.html` for any unknown path;
  its script reads the code from the URL, validates it against the friend-code alphabet
  (`0123456789ABCDEFGHJKMNPQRSTVWXYZ`, 8 chars; O, I and L are folded like in the game) and shows it with a copy button.
- `/c/<CODE>`: Recipe Challenge page (same `404.html` router, same alphabet). Shows the code, an "Open the challenge"
  button (`saffronstreet://challenge/CODE`), the store link and the steps for a fresh install (play the tutorial, then
  open the link again or enter the code in Settings → Challenges). The game builds these links from `CHALLENGE_BASE_URL`.
- `assets/`: app icon, item sprites, `og.png` (1200x630 share image).

The game builds invite links from `INVITE_BASE_URL` on the Nakama host (`https://tontechco.github.io/saffronstreet-site/i/`).

## Later: Universal Links / App Links

`apple-app-site-association` and `assetlinks.json` must be served from the root of a host, which a project page cannot do.
A later step is to add them (and an `/saffronstreet-site/` redirect or paths) via the org's `tontechco.github.io` repo
or a custom domain. Not done yet; do not edit `tontechco.github.io` until then.

Edit the HTML by hand; keep the privacy policy in sync with the game's App Privacy answers (`docs/RELEASE.md` in the game repo).
