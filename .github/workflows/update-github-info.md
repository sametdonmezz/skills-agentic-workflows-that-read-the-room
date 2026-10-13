---
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
engine:
  model: auto
name: update-github-info
network:
  allowed:
    - github.com
    - github.blog
"on":
  schedule:
    - cron: 17 9 * * *
  workflow_dispatch: null
safe-outputs:
  create-pull-request:
    draft: true
    fallback-as-issue: false
    title-prefix: "[mona] "
tools:
  edit: null
  web-fetch: null
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes, using GitHub repository API tools to read repository guidance and reference files. Do not use terminal, CLI, or sandboxed commands to read repository files.

Use web-fetch to read these official sources and any relevant external public guidance:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Update `site/content/github-info.md` with concise, practical updates for readers. Include source context whenever content comes from the GitHub Blog or GitHub Changelog.

Open a pull request for Mona to review. Use a pull request title that mentions Mona or GitHub Info. Do not write directly to `main`; rely on `safe-outputs` with `create-pull-request`.