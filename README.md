# Bowen Yan — academic website

Personal academic website built with [al-folio](https://github.com/alshedivat/al-folio).

Website: https://bowen-yan-research.github.io/

## Content

- `_pages/about.md`: biography and profile
- `_pages/projects.md`: research overview and demonstrations
- `_pages/papers/`: individual paper introductions
- `_bibliography/papers.bib`: publication metadata and links
- `assets/pdf/`: CV and paper PDFs
- `_data/socials.yml`: contact links

## Deployment

GitHub Pages source must be set to **GitHub Actions**. Push to `main` to build and deploy.

## Local development

Use Ruby 3.3.5 and Bundler 4.0.6, with Node.js on PATH:

```sh
bundle install
bundle exec jekyll serve
```

The site uses the upstream MIT-licensed al-folio starter and versioned theme gems. The upstream license is retained in `LICENSE`; paper PDFs and research media retain their respective authors' rights.
