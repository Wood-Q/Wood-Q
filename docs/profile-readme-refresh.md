# GitHub Profile README Refresh

## Context

The repository is a GitHub profile repository. `README.md` is the profile entry point, and `.github/workflows/snake.yml` generates contribution snake SVG files into the `output` branch.

## Dependency Analysis

- `README.md` can safely reference local image assets such as `assets/lin.png` because GitHub renders repository-relative images in profile READMEs.
- The contribution snake image depends on `.github/workflows/snake.yml`, `Platane/snk/svg-only@v3`, and the generated files on the `output` branch.
- The refresh does not change the workflow, token usage, branch names, or snake output paths, so the existing generation chain remains intact.
- The old external stats cards from `github-readme-stats.vercel.app` are removed to make the snake graphic the main lower visual.
- The header style is adapted from `/Users/woodq/FullStack/dodolalorc/README.md`, while personal content and image assets are kept specific to `Wood-Q`.

## Design

The profile uses a lightweight composition:

- Centered typing-svg intro lines for the first impression.
- A short centered interest statement and compact identity tags.
- GitHub and Bilibili badges for confirmed profile links.
- A right-aligned `assets/lin.png` image beside a terminal-style Markdown block.
- A dedicated snake section using the existing light and dark contribution snake SVG outputs.

## Verification

After editing, verify that:

- `README.md` references `assets/lin.png`.
- `README.md` references both light and dark snake SVG outputs.
- `README.md` no longer references `github-readme-stats` or `top-langs`.
- `.github/workflows/snake.yml` is unchanged.
