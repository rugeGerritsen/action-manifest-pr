# action-manifest-pr
GitHub action to automatically create Pull Requests in the manifest repo when updating revisions.

## usage
Please call this action from triggering repo to create manifest PRs automatically (e.g. sdk-nrfxlib)
```yaml
name: handle manifest PR
on:
  pull_request_target:
    types: [opened, synchronize, closed]
    branches:
      - main

jobs:
  create-manifest-pr:
    runs-on: ubuntu-latest
    steps:
      - name: Create manifest PR
        uses: nrfconnect/action-manifest-pr@main
        with:
          token: ${{ secrets.NCS_GITHUB_TOKEN }}
```
