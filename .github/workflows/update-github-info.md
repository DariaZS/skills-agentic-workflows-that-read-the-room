---
emoji: 📰
description: Fetches the latest GitHub Blog and Changelog posts, updates site/content/github-info.md, and opens a pull request for Mona to review.

on:
  schedule:
    - cron: daily
  workflow_dispatch:

permissions:
  contents: read

tools:
  edit:
  web-fetch:

safe-outputs:
  create-pull-request:

network:
  allowed:
    - github.com
    - github.blog
---

# Update GitHub Info

## Task

You are keeping Mona's GitHub Info website up to date with the latest posts from the GitHub Blog and Changelog.

1. Read `notes/mona-notes.md` to understand Mona's editorial guidelines.
2. Read `site/content/github-info.md` to see the current content.
3. Web fetch `https://github.blog/latest/` to find the most recent GitHub Blog posts.
4. Web fetch `https://github.blog/changelog/` to find the most recent GitHub Changelog entries.
5. Update `site/content/github-info.md` with new, noteworthy items:
   - Follow Mona's editorial angle: keep summaries short and practical.
   - Always cite the source (GitHub Blog or GitHub Changelog) for each item.
   - Add new items under the `## Latest GitHub Updates` section.
   - Preserve existing content; only remove items that are clearly outdated.
6. Open a pull request with the proposed changes for Mona to review.

## Pull Request

- Title: `chore: update GitHub info with latest blog and changelog posts`
- Body: describe what was added or changed and include links to the source posts.
- Target branch: `main`
