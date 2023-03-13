<div align="center">
   <img src="https://github.com/gravitational/teleport-actions/raw/main/assets/img/readme-header.png" width=750/>
   <div align="center" style="padding: 25px">
      <a href="https://www.apache.org/licenses/LICENSE-2.0">
      <img src="https://img.shields.io/badge/Apache-2.0-red.svg" />
      </a>
   </div>
</div>
</br>

> Read our Blog: <https://goteleport.com/blog/>

> Read our Documentation: <https://goteleport.com/docs/getting-started/>

# `teleport-actions/setup`

`setup` installs key Teleport binaries into your workflow environment, for
example `tctl`, `tsh` and `tbot`. You can then use these within your workflows.

The GitHub Actions tool cache is used by the `setup` action in order to increase
setup speed and reduce bandwidth usage on self-hosted runners.

Pre-requisites:

- A Linux based runner.

Example usage:

```yaml
on:
  workflow_dispatch: {}
jobs:
  demo-setup:
    runs-on: ubuntu-latest
    steps:
      - name: Install Teleport
        uses: teleport-actions/setup@v1
        with:
          # version must be specified, and exclude the "v" prefix.
          # check https://goteleport.com/download/ for valid releases.
          version: 12.1.0
      - run: tsh # tsh, tbot and tctl will now be available
```
