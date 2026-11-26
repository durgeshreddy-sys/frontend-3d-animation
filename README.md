# Frontend 3D Animation

A Codex skill for React JS, Three.js, React Three Fiber and Tailwind CSS. Start with [SKILL.md](SKILL.md). The [analysis](references/prompt-analysis.md) consolidates all thirteen frontend references and the character-animation brief; [tool selection](references/tool-selection.md) incorporates the fourteen-repository screenshot.

## Install and use

Copy the complete `frontend-3d-animation` directory to `~/.codex/skills/frontend-3d-animation` (or `$CODEX_HOME/skills/frontend-3d-animation`). Do not overwrite an existing skill without reviewing it. Start a new Codex session if it does not appear immediately. This package keeps normal automatic selection enabled.

Example: **Use $frontend-3d-animation to build an interactive 3D hero with React, Three.js, React Three Fiber and Tailwind.**

## Run the example

```bash
cd examples/motion-lab
npm ci
npm run dev
```

Or create a new project using `python3 scripts/scaffold.py /path/to/new-project`. See [starter guide](references/starter.md) for controls, exports and additional example prompts.

## Checks

```bash
python3 -m unittest discover -s tests -v
python3 scripts/validate_motion.py examples/motion-lab/src/motion.json
cd examples/motion-lab
npm test
npm run build
# With the dev server running and Chromium available:
npm run test:browser
```

Python utilities use only the standard library. Browser checks use Playwright as a development dependency. `inspect_asset.py` inspects PNG/glTF/GLB metadata; other formats are reported as unparsed. It never downloads external dependencies.

The original example has a primitive articulated rig and illustrative key poses, not weighted skinning or finished mocap. Spine conversion, arbitrary image-to-3D reconstruction and automatic universal retargeting are documented workflows, not claimed implemented services. See [quality report](references/quality-report.md) for exact test coverage and limits. No third-party reference artwork, Mixamo characters or upstream Spine source is bundled.
