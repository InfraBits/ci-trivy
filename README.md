# Trivy scanner

Scan a container image or SBOM using `trivy`.

Exactly one of `image` or `sbom` must be specified. `sbom` may be a single SBOM file, or a directory
containing SBOM files (`*.spdx`, `*.spdx.json`, `*.cdx`, `*.cdx.json`).

## Example Usage

```
  scan-container:
    runs-on: ubuntu-latest
    steps:
      - uses: infrabits/ci-trivy@main
        with:
          image: ghcr.io/${{ github.repository }}:${{ github.sha }}
          github_token: ${{ secrets.GITHUB_TOKEN }}

  scan-sbom:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: infrabits/ci-trivy@main
        with:
          sbom: sbom.cdx.json
```
