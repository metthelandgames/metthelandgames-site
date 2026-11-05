# metthelandgames-site

Public developer website for **Metthelandgames**, served by GitHub Pages at https://metthelandgames.com.

Google Play, the App Store and AdMob depend on this site. Keep it up:
- `app-ads.txt`: authorized ad sellers. AdMob reads it from the domain root. **If it goes missing, ad serving
  stops and the apps risk removal.**
- `privacy.html`: privacy policy linked from every store listing.
- `support.html`: support and contact page.

Plain static HTML with no build step, on purpose: fewer moving parts means fewer ways to break.

## Games
Home (`index.html`) has a card per game; each game has `games/<slug>/index.html` with its banner, trailer (`trailer.mp4`, hosted
here, so no third-party embeds or cookies), `shots/` and store links. New game: copy a folder, edit it, add a card. **When an iOS app
goes live:** on its page, replace the "Coming soon to the App Store" span with the badge in the comment above it, update Platforms, and add
the footer line. The badges in `badges/` are the official ones, unmodified; Apple's only goes on apps that are on the App Store.
The `studio-ops` compliance watcher checks this site daily.

## DNS (Cloudflare)
The apex `metthelandgames.com` points to GitHub Pages (A/AAAA records, DNS only / grey cloud), and
`www` is a CNAME to `<org>.github.io`. The domain is verified in the GitHub organization's Pages settings.
