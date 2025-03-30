## Olá, eu sou o Enrico!

![Enrico's GitHub stats](https://github-readme-stats.vercel.app/api?username=enrlzzz&show_icons=true&theme=merko)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=enrlzzz&layout=compact)

name: "Static code analysis workflow (CodeQL)"

on:
  push:
    branches:
      - master
  pull_request:
    branches:
      - master

permissions:
  actions: read
  checks: read
  contents: read
  deployments: read
  issues: read
  discussions: read
  packages: read
  pages: read
  pull-requests: read
  repository-projects: read
  security-events: write
  statuses: read

jobs:
  CodeQL-Build:
    # CodeQL runs on ubuntu-latest, windows-latest, and macos-latest
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4.2.2

      # Initializes the CodeQL tools for scanning.
      - name: Initialize CodeQL
        uses: github/codeql-action/init@46a6823b81f2d7c67ddf123851eea88365bc8a67 # v2.13.5
        with:
          languages: javascript

      - name: Perform CodeQL Analysis
        uses: github/codeql-action/analyze@46a6823b81f2d7c67ddf123851eea88365bc8a67 # v2.13.5
