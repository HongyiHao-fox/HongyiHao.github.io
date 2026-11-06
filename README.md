# Hongyi Hao's Personal Website

Source for Hongyi Hao's (郝泓毅) academic homepage, served by GitHub Pages at
**https://hongyihao-fox.github.io/**

The site is a single static HTML page. It has no build step, framework or dependencies beyond a Google Fonts stylesheet.

## Repository layout

```
├── index.html          # The whole site: markup, inline CSS and the bibtex/abstract toggle script
├── data/
│   └── HongyiHao_CV.pdf
├── images/
    ├── <PAPER>/<PAPER>.png   # One folder per publication thumbnail (ECHOES, EEG, HRVO, ...)
    ├── Projects/             # Project thumbnails
    ├── HongyiHao_White.jpg   # Profile photo
    └── HongMing_Logo.png     # Favicon / team logo
```

## Page sections

News · Publications · Research Experiences · Internship Experiences · Personal Honors · Patents and Software Copyrights · Projects · Project team and group

## Local preview

Open `index.html` in a browser, or serve the folder so relative paths behave as they do in production:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Adding a publication

Copy an existing entry in the Publications section of `index.html` (for example the one with `id="ECHOES"`) and change these parts:

1. **Thumbnail.** Put the image in `images/<NAME>/<NAME>.png` and update the `<img src>`.
2. **Title anchor.** `<a href="#NAME" id="NAME">` gives each paper a linkable URL fragment.
3. **IDs.** Each entry uses a shared prefix such as `echoes`:
   - `<article class="paper" id="echoes_paper">`, the container
   - `<div id="echoes_abs" style="display:none">`, the abstract, toggled by `toggleblock('echoes_abs')`
   - `<div id="echoes_paper_bib" style="display:none">`, the BibTeX, toggled by `togglebib('echoes_paper')`

   `togglebib(id)` adds `_bib` to the id it receives, so the BibTeX div must be named `<paper id>_bib`. Every div whose id ends in `_bib` is hidden when the page loads.

## Updating the CV

Replace `data/HongyiHao_CV.pdf` and keep the same filename so existing links keep working.

## Deployment

GitHub Pages serves the `master` branch. Push to `master` and the live site updates within a few minutes:

```bash
git add -A
git commit -m "Update homepage"
git push origin master
```

## Credits

The layout is adapted from the academic homepage templates of [Jon Barron](https://jonbarron.info/) and [Deepak Pathak](https://www.cs.cmu.edu/~dpathak/). `js/hidebib.js` comes from [Andrea Vedaldi](http://www.robots.ox.ac.uk/~vedaldi/) and `js/scramble.js` from [Jeff Donahue](http://jeffdonahue.com/).

## Contact

- Email: Lanyi_adict@outlook.com
- GitHub: [HongyiHao-SXIT](https://github.com/HongyiHao-SXIT)
