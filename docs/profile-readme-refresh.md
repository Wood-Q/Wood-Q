# GitHub Profile README Refresh

## Context

The repository is a GitHub profile repository. `README.md` is the profile entry point, and `.github/workflows/snake.yml` generates contribution snake SVG files into the `output` branch.

## Dependency Analysis

- `README.md` can safely reference local image assets such as `assets/lin.png` because GitHub renders repository-relative images in profile READMEs.
- The contribution snake image depends on `.github/workflows/snake.yml`, `Platane/snk/svg-only@v3`, and the generated files on the `output` branch.
- The GitHub stats card depends on the working `github-readme-stats-two-sand-73.vercel.app` deployment; the default `github-readme-stats.vercel.app` deployment was observed returning `503 DEPLOYMENT_PAUSED`.
- The refresh does not change the workflow, token usage, branch names, or snake output paths, so the existing generation chain remains intact.
- The old wide multi-column stats section is removed; compact GitHub stats and streak cards are stacked beside `assets/lin.png` as the middle visual.
- The header style is adapted from `/Users/woodq/FullStack/dodolalorc/README.md`, while personal content and image assets are kept specific to `Wood-Q`.

## Design

The profile uses a lightweight composition:

- Centered typing-svg intro lines for the first impression.
- A short centered interest statement and compact identity tags.
- GitHub and Bilibili badges for confirmed profile links.
- A centered two-column HTML table pairs stacked GitHub stats and streak cards with a centered `assets/lin.png` image, avoiding Markdown code-block chrome and floating-image misalignment.
- A dedicated snake section using the existing light and dark contribution snake SVG outputs.

## Verification

After editing, verify that:

- `README.md` references `assets/lin.png`.
- `README.md` references both light and dark snake SVG outputs.
- `README.md` references GitHub stats and streak cards and no longer references `top-langs`.
- `.github/workflows/snake.yml` is unchanged.
