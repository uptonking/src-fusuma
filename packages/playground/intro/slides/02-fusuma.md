<!-- section-title: What is Fusuma? -->

## What's Fusuma?

#### _Fusuma is a tool to create slides easily for you.β οΈ_

<br />

- Powerful CLI
- Providing mdx and custom themes
- Presenter mode
- Exporting as PDF
- Improving SEO/OGP

<br />

### just code only Markdown and execute with CLIπ

---

## Procedure

<!-- block-start: grid -->

<!-- block-start: column -->

```shell
$ npm i fusuma -D
$ npx fusuma init
$ tree -a
.
βββ .fusumarc.yml
βββ .github
β   βββ workflows
β       βββ fusuma.yml
βββ slides
β   βββ 0-slide.md
βββ style.css

# --- executable tasks---
$ npx fusuma init          # create scaffold
$ npx fusuma start         # run server for development
$ npx fusuma start-prod    # run server for bundle directory
$ npx fusuma build         # build slides for production
$ npx fusuma deploy        # deploy to github pages
$ npx fusuma pdf           # export as PDF
```

<!-- block-end -->

<!-- block-start: column -->

```json
// package.json

{
  "scripts": {
    "start": "fusuma start",
    "start:prod": "npm run build && fusuma start-prod",
    "build": "fusuma build",
    "deploy": "npm run build && fusuma deploy",
    "pdf": "npm run build && fusuma pdf"
  }
}
```

<!-- block-end -->
<!-- block-end -->
