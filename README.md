# rotorflight-landing-page

The landing page for [Rotorflight](https://github.com/rotorflight), the open source flight control software for RC helicopters.

It is a single static page (`index.html`) with no build step. Documentation lives separately at [doc.rotorflight.org](https://doc.rotorflight.org/).

## Layout

```
index.html        The whole page: markup, styles and a small script
favicon.ico
assets/img/       Logos, hero poster image, Open Collective QR
assets/icons/     Feature illustrations
assets/vid/       Hero background video (WebM + MP4)
```

All asset paths are relative, so the page works both at the GitHub Pages project URL and at a custom domain root.

## Running locally

```
python -m http.server 8000
```

Then open http://localhost:8000/.

## Deployment

Every push to `master` runs `.github/workflows/deploy-gh-pages.yml`, which publishes the repository to the `gh-pages` branch. GitHub Pages serves that branch at:

https://rotorflight.github.io/rotorflight-landing-page/

## Moving to www.rotorflight.org

The `rotorflight.org` domain still points at the old Docusaurus site (`rotorflight-docs`). When it is time to switch:

1. Remove the `CNAME` file from `rotorflight-docs/static/` (or retire that site's Pages deployment) so the domain is free.
2. Add a `CNAME` file to the root of this repository containing `www.rotorflight.org`.
3. In this repository's **Settings > Pages**, set the custom domain to `www.rotorflight.org` and enable **Enforce HTTPS** once the certificate is issued.
4. Check that old deep links (for example `/docs/...`) are handled, e.g. by redirecting them to doc.rotorflight.org.

## Updating for a new release

The release section in `index.html` (`id="release"`) and the hero pill link name the current version. Update the version numbers and highlights there when a new release ships.
