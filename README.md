# GazeMM — project page

Project page for **GazeMM: Robust Off-Angle Iris Recognition via Gaze Manifold Matching**
(Min, Kim, Park, Ryu, Lee — ETRI).

Static HTML, no build step. Deployed with GitHub Pages.

```
.
├── index.html            # main project page
├── supplementary.html    # supplementary material (the paper points readers here)
├── static/
│   ├── css/style.css     # single stylesheet shared by both pages
│   ├── images/           # figures cropped from the manuscript at 600 dpi
│   └── pdfs/             # manuscript PDF
└── .nojekyll             # tell GitHub Pages to serve files as-is
```

## Deploy

```bash
git remote add origin https://github.com/<account>/GazeMM.git
git push -u origin main
```

Then **Settings → Pages → Source: `main` / `/ (root)`**.
The site appears at `https://<account>.github.io/GazeMM/` after ~1 minute.

To preview locally:

```bash
python -m http.server 8000
# open http://localhost:8000
```

## Before pushing

- [ ] **Decide whether to publish `static/pdfs/GazeMM_paper.pdf`.** It is the submitted
      manuscript. ICASSP does not review double-blind and permits preprints, so this is
      normally fine — but delete the file and its button in `index.html` if you would
      rather wait for the decision.
- [ ] Confirm the venue line in `index.html` (`<div class="venue">`) — currently
      "Submitted to ICASSP 2027".
- [ ] Add the arXiv link and remove `aria-disabled="true"` from that button.
- [ ] Check the code repo link. It currently points at
      `github.com/kimyoungwook7/GAZEMM`, matching the paper.
- [ ] Update the BibTeX entry once the paper is accepted.

## Supplementary

`supplementary.html` is a port of `Template_supplemental_v0.2.tex` (Overleaf project),
covering all five items the paper promises the project page will host:

| Paper says | Where it lives |
| --- | --- |
| Dataset statistics | § A, Table S1 + Figs. S1–S2 |
| Baseline configurations | § B, per-method |
| Training settings | § B, proposed method |
| Hyperparameter analyses | § C, Tables S9 ($k$) and S10 ($c$) |
| Extended results | § C, Tables S2–S8 |

**Keep it in sync with the `.tex`.** If the supplemental source changes, the numbers here
have to change too — nothing regenerates automatically.

## Hosting large files

GitHub Pages caps a repo at ~1 GB and individual files at 100 MB, with 100 GB/month of
bandwidth. Keep checkpoints, extracted features and video off this repo — put them on
Hugging Face Hub or Zenodo (which also mints a DOI) and link out.

## Credits

Layout follows the [Nerfies](https://github.com/nerfies/nerfies.github.io) project page
convention, released under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/).
