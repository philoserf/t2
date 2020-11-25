# T2

![Build Status](https://img.shields.io/endpoint.svg?url=https%3A%2F%2Factions-badge.atrox.dev%2Fphiloserf%2Ft2%2Fbadge%3Fref%3Dmain&style=for-the-badge)

## Summary

An example of modern (2020) Amazon Web Services Elastic Kubernetes Service
cluster configuration management using eksctl, managed node pools, manages
addons, and flux2 gitops toolkit.

## Usage

1. edit `cluster.yaml` with desired values
2. edit `bootstrap/flux-sync.yaml` with the desired git remote source
3. edit `base/kube-system` resources with desired add-ons and values
4. run `task bootstrap`
5. prosper

## Contents

- `Taskfile.yml`: see Contributing below
- `cluster.yaml`: the `eksctl` cluster config file
- `/bootstrap/`: files required by bootstrap
- `/base/`: files common to all clusters
- `/development/`: future overlay (non-production workloads)
- `/staging/`: future overlay (pre-production workloads)
- `/production/`: future overlay (production workloads)
- `/tools/`: future overlay (support workloads)

## Contributing

This project uses [Taskfile](https://taskfile.dev). Please install it first.
Then run `task --list`

- check: looks for style and lint issues
- prep: fixes 'easy' lint and style issues
- bootstrap: runs eksctl and install flux2

## License

Copyright © 2020 by Mark Ayers ([mark@philoserf.com](mailto:mark@philoserf.com))

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
