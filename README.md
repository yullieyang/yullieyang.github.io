# yullieyang.github.io

Personal portfolio site for **Yullie Yang** — built with R Markdown and hosted on GitHub Pages.

Live site: <https://yullieyang.github.io>

## Build

The site is a collection of `.Rmd` files rendered to HTML. To rebuild:

```r
rmarkdown::render_site()
```

Open `blog.Rproj` in RStudio and use *Build Website*.

## Structure

- `index.Rmd` — landing page / bio
- `contact.Rmd` — contact info
- `housingstarts.Rmd`, `employeeattirtionprediction.Rmd`, `dbsql1.Rmd`, `optimization1.Rmd`, `stat1.Rmd`, `visualization{1,2,3}.Rmd` — individual project / analysis pages
- `files/` — downloadable assets (resume PDF, project notebooks, Tableau workbooks)
- `images/` — site graphics
