# charly-jupyter

The `charly-jupyter` family — the Jupyter / data-science image skills.

The `charly-jupyter` candy is a **concept candy**: it ships no install content
and owns the `jupyter` family of `skill:` entities whose names have no namesake
candy. It currently carries three entities:

- `jupyter-layer` — lightweight JupyterLab with real-time collaboration
  (`jupyter-collaboration`) on port 8888; no GPU required.
- `jupyter-ml-layer` — the full CUDA ML stack plus JupyterLab, with the CRDT MCP
  server, on port 8888.
- `unsloth-studio-layer` — the Unsloth Studio fine-tuning web UI on ports
  8888/8000 with vLLM inference; the Tier 2 environment-owner meta-layer that
  composes `llama-cpp` + `unsloth` and owns `pixi.toml`.

The rest of the `jupyter` family is owned by sibling repos (`pod-jupyter`,
`pod-jupyter-ml`, `layer-jupyter-mcp`, `distro-fedora`, `layer-llama-cpp`,
`layer-unsloth`, `pod-unsloth-studio`, and the `layer-notebook-*` data
candies). `candy/plugin-marketplace` regenerates the standalone
[opencharly/marketplace](https://github.com/opencharly/marketplace) corpus from
these entities, so the skills are authored here and projected there.

## What it provides

| Property | Value |
|---|---|
| Layer / candy | `charly-jupyter` (concept candy) |
| Install content | none — a `true` no-op `plan:` |
| Owns | 3 `skill:` entities: `jupyter-layer`, `jupyter-ml-layer`, `unsloth-studio-layer` |
| Projected to | `marketplace/jupyter/skills/` |
| Service / port | none |

## How to use it

This repo is consumed as a **skill source**, not as an image layer. Edit the
`skill:` entities in `charly.yml`; the marketplace regeneration projects them
into `/charly-jupyter:*` pages. To reference the repo directly, compose it in a
box. A box is a `candy:` node that carries the box's `base:` image and a nested
`candy:` list of layer refs (the nested `candy:` is the composition list; the
outer `candy:` is the box body):

```yaml
my-box:
  candy:                  # the box body (an IMAGE is a `candy:` node carrying `base:`)
    base: fedora          # the box's base image
    candy:                # the box's composition list
      - '@github.com/opencharly/layer-charly-jupyter:v2026.265.1928'
```

The Jupyter images themselves are deployed through the `pod-jupyter` /
`pod-jupyter-ml` / `pod-unsloth-studio` boxes; the skills here document the
candies those boxes compose.

## Layout

- `charly.yml` — the `charly-jupyter:` concept candy entity plus three `skill:`
  entities (`jupyter-layer`, `jupyter-ml-layer`, `unsloth-studio-layer`).
- `.github/workflows/tag-on-merge.yml` — CalVer tag + `CHANGELOG/` on merge.
- `README.md` — this user overview.

## Related

- Owning skills: `/charly-jupyter:jupyter-layer`,
  `/charly-jupyter:jupyter-ml-layer`, `/charly-jupyter:unsloth-studio-layer`
- Authoring reference: `/charly-image:layer`
- Sibling images: `opencharly/pod-jupyter`, `opencharly/pod-jupyter-ml`,
  `opencharly/pod-unsloth-studio`
- [`opencharly/marketplace`](https://github.com/opencharly/marketplace) — the projected corpus
- [`opencharly/charly`](https://github.com/opencharly/charly) — the charly CLI and image builder
- [`opencharly/opencharly`](https://github.com/opencharly/opencharly) — the umbrella
