# Trivy scanner

Scan a container image using `trivy`.

## Example Usage

```
  scan-container:
    runs-on: ubuntu-latest
    steps:
      - uses: infrabits/ci-trivy@main
        with:
          image: ghcr.io/${{ github.repository }}:${{ github.sha }}
          github_token: ${{ secrets.GITHUB_TOKEN }}
```
