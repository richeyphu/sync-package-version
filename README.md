# 🚀 Sync Package Version

Automatically updates `package.json` to match the latest GitHub release tag.

## 📌 Features

✅ **Syncs `package.json` version** to match the latest **GitHub release tag**  
✅ **No manual version bumps** – Just create a release, and this action updates `package.json` for you  
✅ **Works with npm, pnpm, and yarn projects**  
✅ **Lightweight & Fast** – Uses **Bash & jq**, no extra dependencies required

## 🔧 Usage

### 📝 Add to your workflow (`.github/workflows/release.yml`)

```yaml
name: Release

on:
  release:
    types: [published]

jobs:
  sync-version:
    runs-on: ubuntu-latest
    steps:
      - name: Sync package.json version
        uses: richeyphu/sync-package-version@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

### 🎯 What Happens?

1. Extracts the **release tag** (e.g., `v1.2.3`)
2. Updates the `package.json` **version field**
3. Commits & pushes the changes

## 📥 Inputs

| Name           | Description                        | Required | Default |
| -------------- | ---------------------------------- | -------- | ------- |
| `github-token` | GitHub token with repo permissions | ✅ Yes   | N/A     |

## 📜 License

Licensed under the [**MIT License**](LICENSE).
