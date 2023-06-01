# docker-atlantis
Custom [Atlantis](https://github.com/runatlantis/atlantis) Docker image repository.

This repository maintains a custom Atlantis Docker image. 
Extra functionality:
- AWS CLI
- Infracost

Only **debian** is automatically built for now (alpine takes too long to build).

## How to
1. Modify `Dockerfile` or `version.env`. `version.env` contains the base Atlantis version.
2. Create PR, which trigger the docker-pr.yaml workflow.
3. After approvals and testing, PR will be merged and built images and commit automatically tagged

## Tagging strategy
- PR
  - `<$atlantis-version>-pr<$PR-number>-alpha-<$os>`, e.g. `v0.24.1-pr2-alpha-debian`
  - `<$atlantis-version>-<$commit-sha>-<$os>`, e.g. `v0.24.1-23523572395472943572934552452352-debian`
- main
  - `<atlantis-version>-latest-<$os>`, e.g. `v0.24.1-latest-debian`
  - `<$atlantis-version>-v<$single-number-version>-<$os>`, e.g. `v0.24.1-v2-debian`
    - `<$single-number-version>` is incremented +1 with each non-Atlantis version change to the Dockerfile
