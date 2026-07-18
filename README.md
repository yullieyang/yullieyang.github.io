# yullieyang.github.io

Personal portfolio site for **Yullie Yang** — an Applied AI Builder with a
quantitative analytics background, building AI agents, workflow
automations, and evaluation-first tools alongside reproducible financial /
economic research workflows.

**Live site:** <https://yullieyang.github.io>

## Architecture

The landing page and project case-study pages are plain static HTML
sharing one stylesheet at `assets/site.css` — no Jekyll templating, no R
Markdown render step, no external CSS framework, no build step. GitHub
Pages serves everything directly. A `.nojekyll` file disables Jekyll
processing across the site.

Earlier coursework pages (housing starts, attrition, visualization series)
were rendered from `.Rmd` to `.html` in a previous R Markdown setup. The
built HTML files are kept and linked from the landing page; the source
`.Rmd` files are retained as historical artifacts and are not part of the
build path anymore.

## Featured GitHub repos

Featured GenAI / LLM solutions (each with a case-study page under `projects/`):

- [agentic-ai-evaluation-platform](https://github.com/yullieyang/agentic-ai-evaluation-platform)
  — LLM-based QA agent + reviewer agent for model-monitoring anomaly review,
  with schema-validated findings, calibration/failure analysis, and a
  Streamlit dashboard. Canonical results are from an offline mock provider.
- [cardnews](https://github.com/yullieyang/cardnews)
  — Claude-powered CLI that turns a topic into a structured 10-slide JSON
  briefing, rendered by a deterministic Puppeteer pipeline into a reviewable
  PNG deck.

Selected quantitative & applied AI work:

- [product-ab-experiment](https://github.com/yullieyang/product-ab-experiment)
  — end-to-end experimentation case study (SRM, power/MDE, CUPED, guardrails).
- [r-macro-trade-commodity-forecast](https://github.com/yullieyang/r-macro-trade-commodity-forecast)
  — reproducible R macro / trade / commodity pipeline with FX pass-through.
- [cre_stress_test](https://github.com/yullieyang/cre_stress_test)
  — bilingual Python + R stress-testing portfolio demo on public data.
- [llm-research-workflow-assistant](https://github.com/yullieyang/llm-research-workflow-assistant)
  — responsible AI workflow prototype for research QA and documentation.

## Editing the site

Open `index.html` or a page under `projects/` in any editor. Shared styles
live in `assets/site.css`; content is plain HTML. To preview locally:

```bash
python3 -m http.server 8080
# then open http://localhost:8080 in a browser
```

## Repository layout

```
yullieyang.github.io/
├── index.html                       # Landing page
├── projects/
│   ├── agentic-ai-evaluation-platform.html  # Featured GenAI case study
│   └── cardnews.html                        # Featured GenAI case study
├── assets/site.css                  # Shared stylesheet
├── .nojekyll                        # Disable Jekyll processing
├── README.md
├── files/                           # Resume PDF + downloadable artifacts
├── images/                          # profile_pic.jpg + figure assets + agentic/ + cardnews/ screenshots
├── application-materials/           # Local-only, gitignored — company-specific application notes
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
