# 🔄 Sync Package Version

Automatically updates `package.json` to match the latest GitHub release tag.

## 📌 Features

✅ **Syncs `package.json` version** to match the latest **GitHub release tag**  
✅ **No manual version bumps** – Just create a release, and this action updates `package.json` for you  
✅ **Works with npm, pnpm, and yarn projects**  
✅ **Lightweight & Fast** – Uses **Bash & jq**, no extra dependencies required

## 🔧 Usage

### 📝 Add to your workflow

Create a new workflow file (e.g., `.github/workflows/release.yml`) in your repository:

```yaml
name: 🚀 Release

on:
  release:
    types: [published]

jobs:
  sync-version:
    runs-on: ubuntu-latest
    steps:
      - name: Sync package.json version 🔄
        uses: richeyphu/sync-package-version@v1
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
```

### 🎯 What happens?

1. Extracts the **release tag** (e.g., `v1.2.3`)
2. Updates the `package.json` **version field**
3. Commits & pushes the changes

## 📥 Inputs

| Name           | Description                              | Required | Default                    |
| -------------- | ---------------------------------------- | -------- | -------------------------- |
| `token`        | GitHub token with repo permissions       | ✅ Yes   | N/A                        |
| `repository`   | GitHub repository (e.g., `owner/repo`)   | ❌ No    | `${{ github.repository }}` |
| `branch`       | Branch to push changes to                | ❌ No    | `main`                     |
| `skip-ci`      | Skip CI checks for the commit            | ❌ No    | `false`                    |
| `pull-request` | Create a pull request instead of pushing | ❌ No    | `false`                    |

## 📜 License

Licensed under the [**MIT License**](LICENSE).
