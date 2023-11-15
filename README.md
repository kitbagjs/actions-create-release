# actions-create-release
## Description
A github action creating releases

## Environment Variables/Secrets

| Env Var/Secret | Desription | Required |
|-------|------------|----------|
| GITHUB_TOKEN | The Github token to use for creating the release.. | true |

## Usage
```yaml
on:
  push:
    tags:
      - 'v*' # Push events to matching v*, i.e. v1.0, v20.15.10

name: Create Release

jobs:
  release:
    name: Create Release
    runs-on: ubuntu-latest
    permissions: 
      contents: write
    
    steps:
      - uses: kitbagjs/actions-create-release@main
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
