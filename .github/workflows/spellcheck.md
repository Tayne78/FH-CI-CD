name: 'spellcheck'
on:
  pull_request:
      branches: ["main"]
  push:
      branches: ["main"]

jobs:
  spellcheck:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: matheus23/md-spellcheck-action@v4.2.2
        with:
          files-to-check: "*.md"
          files-to-exclude: "LICENSE.md" # optional
          words-to-ignore-file: ./words-to-ignore.txt
