# metthelandgames-site

Public developer website for **Metthelandgames**, served by GitHub Pages at https://metthelandgames.com.

Google Play, the App Store and AdMob depend on this site. Keep it up:
- `app-ads.txt`: authorized ad sellers. AdMob reads it from the domain root. **If it goes missing, ad serving
  stops and the apps risk removal.**
- `privacy.html`: privacy policy linked from every store listing.
- `support.html`: support and contact page.

Plain static HTML with no build step, on purpose: fewer moving parts means fewer ways to break.
The `studio-ops` compliance watcher checks this site daily.

## DNS (Cloudflare)
The apex `metthelandgames.com` points to GitHub Pages (A/AAAA records, DNS only / grey cloud), and
`www` is a CNAME to `<org>.github.io`. The domain is verified in the GitHub organization's Pages settings.
