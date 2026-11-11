# NodeWave website

Static presentation site (plain HTML and CSS, no build step). `.github/workflows/pages.yml` publishes the repository to GitHub Pages on every push to `main` (and daily, to refresh the numbers bar from the app repository); the setting is *Settings -> Pages -> Build and deployment -> Source: GitHub Actions*. The app lives in [sputlab/nodewave](https://github.com/sputlab/nodewave); project documents and the changelog are there.

- `index.html`: the home page (hero, screenshot carousel, features, timeline, security, download)
- `support.html`: ways to support the project (devices, tests, word of mouth, community, donations)
- `transparency.html` + `transparency.json`: public ledger of money received/spent and in-kind contributions (edit the JSON to add entries)
- `donate.html`: PayPal donation page, adapted from sputlab.com/donate (no donor list: that needs a server)
- `test-report.html`: the test list and report form; the report is composed in the browser and sent with a `mailto:` link to testreport@nodewave.org (the site has no server), with copy and download as fallbacks
- `style.css`, `site.js`: shared styles and the carousel / timeline scripts (`?reveal=all` shows every timeline item at once, for previews)
- `images/icon.png`: the app icon; `assets/screens/`: the screenshots
- `CNAME`: the custom domain, `nodewave.org` (GitHub Pages reads it from here)
- `.nojekyll`: serve the files as they are

To see it locally: `python3 -m http.server` and open http://localhost:8000.

DNS for the custom domain: an `A` record set pointing `nodewave.org` to GitHub Pages (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153) and a `CNAME` record `www` pointing to `sputlab.github.io`; then tick *Enforce HTTPS* in Settings -> Pages.

Keep in step with the app: the timeline on the home page, the feature cards, and the test catalogue in `test-report.html` (the `GROUPS` array and `APP_VERSIONS`) when a release changes behaviour.
