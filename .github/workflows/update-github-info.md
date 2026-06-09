---
name: update-github-info
description: Draft concise GitHub Info updates for Mona from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: '[mona] '
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making any changes.

Use these sources:
- `notes/mona-notes.md`
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Update `site/content/github-info.md` with a new section named `Latest GitHub Updates`.
Include at least one concise update for readers, and keep the writing short and practical.
When a sentence comes from the GitHub Blog or GitHub Changelog, mention the source clearly.

Use `safe-outputs` with `create-pull-request` so you do not write directly to `main`.
Open a pull request for Mona to review, and make the title clearly mention Mona or GitHub Info.