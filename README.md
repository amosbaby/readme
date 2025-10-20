# 🤓 About Me
Work at [Tehang](https://github.com/cntehang)

[![Amos's github stats](https://github-readme-stats.vercel.app/api?username=amosbaby)](https://github.com/anuraghazra/github-readme-stats)
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=amosbaby)](https://github.com/anuraghazra/github-readme-stats)

name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:
  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: Generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - name: Push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}



## 🐍 Contribution Snake

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ark-65/ark-65/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/ark-65/ark-65/output/github-contribution-grid-snake.svg">
  < img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/ark-65/ark-65/output/github-contribution-grid-snake.svg">
</picture>
