# yullieyang.github.io

Personal portfolio site for **Yullie Yang** — quantitative analyst building
reproducible financial / economic research workflows and AI-assisted QA /
documentation systems.

**Live site:** <https://yullieyang.github.io>

## Architecture

The landing page is a single self-contained `index.html` with embedded CSS
— no Jekyll templating, no R Markdown render step, no external CSS
framework. GitHub Pages serves it directly. A `.nojekyll` file disables
Jekyll processing across the site.

Earlier coursework pages (housing starts, attrition, visualization series)
were rendered from `.Rmd` to `.html` in a previous R Markdown setup. The
built HTML files are kept and linked from the landing page; the source
`.Rmd` files are retained as historical artifacts and are not part of the
build path anymore.

## Featured GitHub repos

- [r-macro-trade-commodity-forecast](https://github.com/yullieyang/r-macro-trade-commodity-forecast)
  — reproducible R macro / trade / commodity pipeline with FX pass-through.
- [cre_stress_test](https://github.com/yullieyang/cre_stress_test)
  — bilingual Python + R stress-testing portfolio demo on public data.
- [llm-research-workflow-assistant](https://github.com/yullieyang/llm-research-workflow-assistant)
  — responsible AI workflow prototype for research QA and documentation.

## Editing the landing page

Open `index.html` in any editor. The CSS is inline in a single `<style>`
block at the top; the content is plain HTML below it. To preview locally:

```bash
python3 -m http.server 8080
# then open http://localhost:8080 in a browser
```

## Repository layout

```
yullieyang.github.io/
├── index.html                       # Landing page (self-contained)
├── .nojekyll                        # Disable Jekyll processing
├── README.md
├── files/                           # Resume PDF + downloadable artifacts
├── images/                          # profile_pic.jpg + figure assets
├── housingstarts.html               # Coursework: rendered HTML
├── employeeattirtionprediction.html # Coursework: rendered HTML
├── visualization{1,2,3}.html        # Coursework: rendered HTML
├── *.Rmd                            # Source for earlier coursework HTMLs (not in build path)
└── site_libs/                       # Bootstrap / font-awesome assets used by the coursework HTMLs
```

## Notes

- The repo previously relied on `rmarkdown::render_site()` to build the
  landing page from `index.Rmd`, but `_site.yml` and the custom `styles.css`
  were never committed, so the rendered site fell back to a default Jekyll
  README view. The new `index.html` removes that build dependency.
- If you want to revive the R Markdown site later, restore a `_site.yml`
  and `styles.css`, then run `rmarkdown::render_site()` — the source `.Rmd`
  files are still here.
