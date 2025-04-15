# 🏷️ GitHub Labels Repository

This repository contains a reusable and version-controlled set of GitHub issue/PR labels in YAML (or JSON) format. 
It is designed to help you maintain consistent labeling across multiple repositories.

## 📌 Why use shared labels?

- ✅ Consistency across all your GitHub repos
- 🎯 Clear triage, prioritization, and contribution flows
- 🔁 Easily syncable using [EndBug/label-sync](https://github.com/EndBug/label-sync)
- 🔒 Version-controlled and collaborative

> You can mix and match based on the needs of each project.

## ⚙️ How to Use

To sync labels to a repository using [EndBug/label-sync](https://github.com/EndBug/label-sync), you can copy or reference this file directly.

### 🔁 Example GitHub Actions Workflow

> You can see the example of labels [here](https://github.com/justedlev/github-labels/labels)


```yaml
name: Sync Labels

on:
  workflow_dispatch:

jobs:
  sync-labels:
    runs-on: ubuntu-latest

    steps:
      - name: Sync labels
        uses: EndBug/label-sync@v2
        with:
          config-file: |
            https://raw.githubusercontent.com/justedlev/github-labels/main/area.yml
            https://raw.githubusercontent.com/justedlev/github-labels/main/status.yml
            https://raw.githubusercontent.com/justedlev/github-labels/main/language.yml
            https://raw.githubusercontent.com/justedlev/github-labels/main/type.yml
            https://raw.githubusercontent.com/justedlev/github-labels/main/priority.yml
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
