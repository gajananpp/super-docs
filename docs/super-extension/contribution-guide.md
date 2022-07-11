---
position: 1
---

# Contribution Guide

## Project structure
```bash
root
├── package.json
├── src
│   ├── extension                               # Browser Extension src
│   │   ├── background.ts                       # Extension background entrypoint
│   │   ├── configure                           # Extension configuration/options page
│   │   ├── content_scripts                     # Extension foreground. Scripts injected in pages(including their iframes) of all tabs
│   │   │   ├── captureElement.ts               # Element xPath capturer
│   │   │   ├── captureTable.ts                 # Table element xPath capturer
│   │   │   ├── superappWidget                  # Side widget
│   │   ├── manifest.json                       # Extension manifest
│   │   ├── service_worker                      # Part of extension background
│   └── messaging_host                          # Native Messaging Host src
├── webpack.config.js
└── yarn.lock
```

## Git Workflow 

When making changes, create a new branch from **`development`** branch.
```bash
git checkout -b new-feature-1
```

Make your changes

Whenever syncing remote changes, do it with rebase
```bash
git pull --rebase origin development
```

Once changes done, push your changes to remote repository under same branch name
```bash
git push origin new-feature-1
```

Create a PR from your branch to **`development`** branch. 

Make and push if any required changes before approval to your branch. Closing and opening a new PR is not required.

:::note To merger
When merging PR, merge it with default merge strategy i.e. merging with merge commit.
:::