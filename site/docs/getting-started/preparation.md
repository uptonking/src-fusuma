---
id: preparation
title: Preparation
sidebar_label: Preparation
---

## Installing Fusuma

Fusuma requires Node >= 12.x.

```sh
$ npm i fusuma -D # yarn add fusuma --dev
```

## Directory Structure

The default directory name is `slides` and Fusuma provides `init` command so it's better to use it.

```sh
$ mkdir slides && echo '# Helloπ' > slides/title.md
$ tree -a
.
βββ slides
    βββ title.md

1 directory, 1 files

# or use init command

$ npx fusuma init
$ tree -a
.
βββ .fusumarc.yml
βββ .github
β   βββ workflows
β       βββ fusuma.yml
βββ slides
β   βββ 0-title.md
βββ style.css

1 directory, 3 files
```

### Slide Loading Order

```sh
.
βββ .fusumarc.yml       <-- [optional] the configuration file
βββ index.js            <-- [optional] js extending fusuma
βββ slides              <-- [required] slides written by Markdown or HTML
β   βββ 0-title.md
β   βββ 01-content.md
β   βββ 02-body
β   β   βββ 0-title.md
β   βββ 03-end.md
βββ style.css           <-- [optional] css extending fusuma
```

> A file extension doesn't matter either `.md` or `.mdx`.

Searching slides are based on root hierarchy, and searching order is **numeric, alphabetical**.

The slide display order is as follows.

```sh
0-title.md -> 01-content.md -> 0-title.md(in 02-body) -> 03-end.md
```

## package.json

It is good to define in pacakge.json as follows.

```json
{
  "start": "fusuma start",
  "start:prod": "fusuma start-prod",
  "build": "fusuma build",
  "deploy": "npm run build && fusuma deploy",
  "pdf": "npm run build && fusuma pdf"
}
```
