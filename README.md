# Dastanverse

One-page company website for Dastanverse. Plain HTML and CSS; no build or installation needed.

## Files

- `index.html`: the complete website, including styles and favicon.
- `.nojekyll`: serve the site directly on GitHub Pages.
- `DOMAIN-SETUP.md`: GitHub Pages and GoDaddy setup steps.

## Preview locally

```sh
python3 -m http.server 8766
```

Open http://localhost:8766. Run the command from this folder.

## Publish to GitHub Pages

This folder is an independent Git repository. Create an empty GitHub repository named `dastanverse` under your chosen account. A public repository supports Pages on GitHub Free. Do not add a README or other files during creation.

For the connected `highelf` account:

```sh
git remote add origin https://github.com/highelf/dastanverse.git
git push -u origin main
```

Alternatively, with the GitHub CLI, create and upload in one step:

```sh
gh repo create highelf/dastanverse --public --source=. --remote=origin --push
```

Use one approach, not both. Then open repository Settings → Pages. Select “Deploy from a branch”, branch `main`, folder `/ (root)`, and Save. After deployment, visit https://highelf.github.io/dastanverse/.

Follow DOMAIN-SETUP.md after this URL works. No custom domain is configured in this repository yet, so the initial GitHub Pages URL can be tested first.

## Updates

Edit `index.html`, preview, then:

```sh
git add index.html
git commit -m "Update website"
git push
```

GitHub Pages publishes pushes automatically once configured.

## Logo

Selected wordmark: Dastanverse with capital D, Gill Sans weight 600 and an orange period. The font uses installed system fonts with fallbacks; Gill Sans is not bundled, so its appearance may differ on other devices.
