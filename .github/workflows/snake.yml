name: Generate cosmic contribution snake

on:
  workflow_dispatch:
  push:
    branches:
      - main
      - master
  schedule:
    - cron: '15 2 * * *'

permissions:
  contents: write

jobs:
  snake:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - name: Generate muted-pink snake SVGs
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: SIMMI5KUMARI
          outputs: |
            dist/github-snake.svg?color_snake=%23a97894&color_dots=%23f5eef2,%23e8dce5,%23d3a7bc,%23b889a2,%23825c7c
            dist/github-snake-dark.svg?color_snake=%23d3a7bc&color_dots=%2310131f,%233a2e43,%236b4d68,%239e718f,%23d3a7bc
      - name: Publish SVGs to output branch
        uses: crazy-max/ghaction-github-pages@v3.2.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
