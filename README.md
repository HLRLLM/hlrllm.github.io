# Hear, Localize, and Reason

Project page for **"Hear, Localize, and Reason: Spatially Aware Scene Understanding for
Audio-Visual LLMs"** (NeurIPS 2026).

Live site: https://hlrllm.github.io

## Structure

```
index.html              # the page
static/css, static/js   # Nerfies / Bulma template assets
static/images/          # figures exported from the camera-ready PDF
.nojekyll               # serve files as-is (no Jekyll processing)
```

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## TODO

- [ ] Replace the placeholder `href="#"` links (arXiv / Paper / Code / Data) — `index.html`, search for `TODO`
- [ ] Add demo videos / audio samples and an interactive data viewer
- [ ] Release the HLR-AVSceneQA data and link it from the page

## Regenerating the figures

Figures are cropped from the camera-ready PDF at 300 dpi with `poppler` (`brew install poppler`)
and downscaled to 1700 px wide:

```bash
pdftoppm -f <page> -l <page> -r 300 -png -singlefile -x X -y Y -W W -H H paper.pdf out
sips -Z 1700 out.png
```

## Credits

Template adapted from [Nerfies](https://nerfies.github.io/) (CC BY-SA 4.0).
