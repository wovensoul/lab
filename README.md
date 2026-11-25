# lab

Small standalone experiments. Each top-level folder is a static app deployed to its own Cloudflare Pages project.

| folder | app | domain |
| --- | --- | --- |
| `automata/` | cellular automata visualizer | automata.jeffreychen.work |
| `shape-art/` | geometrizes a photo into triangles | shape-art.jeffreychen.work |

## Running locally

No build step. Serve the repo root and open a folder:

```
python -m http.server 8127
```

## Adding an app

1. Make a folder with an `index.html`.
2. Add the folder name to `matrix.app` in `.github/workflows/deploy.yml`. The first deploy creates a Pages project with that name.
3. In Cloudflare, open the project, go to Custom domains, and add a `jeffreychen.work` subdomain.

## Deploys

Pushes to `main` deploy to production; pull requests get preview URLs. The workflow needs the repo secrets `CLOUDFLARE_API_TOKEN` and `CLOUDFLARE_ACCOUNT_ID`.
