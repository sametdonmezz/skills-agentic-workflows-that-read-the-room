---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
engine:
  model: auto
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes, using GitHub repository API tools to read repository guidance and reference files. Do not use terminal, CLI, or sandboxed commands to read repository files.

Use web-fetch to read these official sources and any relevant external public guidance:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Update `site/content/github-info.md` with concise, practical updates for readers. Include source context whenever content comes from the GitHub Blog or GitHub Changelog.

Open a pull request for Mona to review. Use a pull request title that mentions Mona or GitHub Info. Do not write directly to `main`; rely on `safe-outputs` with `create-pull-request`.