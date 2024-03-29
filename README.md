# docker-atlantis
[<img src="https://lablabs.io/static/ll-logo.png" width=350px>](https://lablabs.io/)

We help companies build, run, deploy and scale software and infrastructure by embracing the right technologies and principles. Check out our website at <https://lablabs.io/>

---

## Description
Custom [Atlantis](https://github.com/runatlantis/atlantis) Docker image repository.

Extra functionality:
- AWS CLI
- Infracost

Only **debian** image is automatically built for now (**alpine** ARM build is failing).

## How to install
Deploy Atlantis according to the official guide https://www.runatlantis.io/docs/deployment.html.

Available custom Atlantis Docker images are located here https://github.com/lablabs/docker-atlantis/pkgs/container/atlantis.
- Latest release debian image for specific Atlantis version:
```shell
ghcr.io/lablabs/atlantis:<$atlantis-version>-latest-debian
```
- Specific released debian version:
```shell
ghcr.io/lablabs/atlantis:<$atlantis-version>-v<$release-version>-debian
```

## Tagging strategy
- PR
  - `<$atlantis-version>-pr<$PR-number>-alpha-<$os>`, e.g. `v0.24.1-pr2-alpha-debian`
  - `<$atlantis-version>-<$commit-sha>-<$os>`, e.g. `v0.24.1-23523572395472943572934552452352-debian`
- main
  - `<$atlantis-version>-latest-<$os>`, e.g. `v0.24.1-latest-debian`
  - `<$atlantis-version>-v<$release-version>-<$os>`, e.g. `v0.24.1-v2-debian`
    - `<$release-version>` is incremented +1 with each non-Atlantis version change to the Dockerfile

## How to update
1. Modify `version` if you want to try a new Atlantis version
2. Make other changes you want
3. Create a PR.

## Contributing
Check [.github/CONTRIBUTING.md](.github/CONTRIBUTING.md) for guideline on how to contribute.

## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

See [LICENSE](LICENSE) for full details.

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.
