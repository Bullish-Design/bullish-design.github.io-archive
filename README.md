# Bullish Design

The site presents mechanical and industrial product design consulting, design notes, and selected digital work. Hugo builds it through siteman.

## Site structure

- `.siteman/hugo.toml` sets the root URL, palette, navigation, and theme order.
- `content/` holds the homepage, About, Work, Design Notes, and Contact pages.
- `static/images/` holds the site logo, illustrations, and social preview.
- `.siteman/layouts/` contains site-owned social metadata, contact, and navigation overrides.
- `.github/workflows/siteman-deploy-github-pages.yml` publishes the Hugo build to GitHub Pages.

Roxo Flex renders the pages. Siteman supplies the build commands. The site lists Roxo Flex before `siteman-default`, which provides fallback layouts.

## Edit content and settings

Edit the homepage sections in `content/_index.md`. Add or revise pages in their matching `content/` section. Keep project details tied to repository evidence. Keep design notes tied to their linked sources.

Edit the palette, navigation labels, page title, and contact link in `.siteman/hugo.toml`. Store new illustrations under `static/images/`. Edit `social-card.svg`, then render its preview with:

```sh
devenv shell -- rsvg-convert -w 1200 -h 630 -o static/images/social-card.png static/images/social-card.svg
```

## Build and verify

Devenv locks siteman and Nixpkgs in `devenv.lock`. Hugo locks Roxo Flex in `go.mod` and `go.sum`. The theme snapshot lives in `_vendor/`.

The siteman input is private, so local contributors need access to the Bullish Design repository. Add a fine-grained `SITEMAN_READ_TOKEN` repository secret with read-only access to the siteman repository. GitHub Actions then runs `siteman-check` and builds the site from source.

Until that secret exists, GitHub Actions deploys the verified Siteman snapshot in `pages-static/`. Refresh this snapshot after a local build when you need to publish before the secret is available:

```sh
devenv shell -- siteman-build
rm -rf pages-static
cp -a public pages-static
```

```sh
devenv shell -- siteman-serve
devenv shell -- siteman-build
devenv shell -- siteman-check
```

After changing the Roxo Flex version in `.siteman/hugo.toml`, sync and vendor the theme:

```sh
devenv shell -- siteman-sync
devenv shell -- hugo --config .siteman/hugo.toml mod vendor
```

Set GitHub Pages to use GitHub Actions. The workflow uses the repository root URL, `https://bullish-design.github.io/`.
