name: Validate documentation

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  markdown:
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20

      - name: Lint Markdown files
        run: npx markdownlint-cli2 "**/*.md"

      - name: Confirm required project files exist
        run: |
          test -f README.md
          test -f SKILL.md
          test -f LICENSE
          test -f CONTRIBUTING.md
          test -f CHANGELOG.md
          test -f CODEOWNERS
