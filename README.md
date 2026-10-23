# charly-jupyter — retired

> **RETIRED — this repo publishes nothing.** All 3 `jupyter`-family skills live in the
> repo that holds the code, plugin or config each one documents (the table below).
> Nothing is authored, built, deployed or consumed here: a change to a `jupyter`-family
> skill is a change at its destination repo, in the same pull request as the entity it
> documents.

**This repo no longer authors a skill.** It was the `charly-jupyter` concept candy: a `true`-no-op `plan:` and 3 `skill:` entities, with the prose in `.agents/skills/`.
Under `AGENTS.md` Part II #5 a skill lives in the repo whose code,
plugin or config it describes — and this repo holds none of them (measured before the
change: **0 `.go`, 0 `.cue`, no `candy/` directory**) — so all of them moved, byte-identically,
to the repos that do:

| Skill | Now authored in | The entity that owns it |
|---|---|---|
| `jupyter-layer` | [`opencharly/pod-jupyter`](https://github.com/opencharly/pod-jupyter) | the `jupyter` candy it documents |
| `jupyter-ml-layer` | [`opencharly/pod-jupyter-ml`](https://github.com/opencharly/pod-jupyter-ml) | the CUDA ML jupyter box |
| `unsloth-studio-layer` | [`opencharly/pod-unsloth-studio`](https://github.com/opencharly/pod-unsloth-studio) | the `unsloth-studio` box |

**The addresses did not change.** Every skill keeps its `jupyter` family at its
destination node, so `/charly-jupyter:<skill>` still resolve — they are simply authored
where the entity is implemented. The move is the rule `AGENTS.md` Part II #5 states, tracked
in [opencharly/opencharly#600](https://github.com/opencharly/opencharly/issues/600).

## What remains here

| Property | Value |
|---|---|
| Layer / candy | `charly-jupyter` (drained concept candy) |
| Install content | none — a `true` no-op `plan:` |
| Owns | nothing — 0 `skill:` entities |
| Service / port | none |

Do not compose, reference or edit this repo: the skills, their routing nodes and their
prose all live at the destinations above, and this repo's retirement is tracked in
[opencharly/opencharly#600](https://github.com/opencharly/opencharly/issues/600).
