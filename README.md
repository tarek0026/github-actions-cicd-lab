# GitHub Actions CI/CD Lab

A small static website used to practice Git branching and a sequential GitHub
Actions workflow.

## Run locally

Open `index.html` in a web browser. The page uses plain HTML, CSS, and
JavaScript, so no package installation or build step is required.

## Git branching workflow

The lab uses `main` for the stable version, `develop` for integration, and
`feature/lab-content` for a focused change. Feature work is merged into
`develop`, then `develop` is merged into `main`.

## CI/CD workflow

The GitHub Actions workflow at `.github/workflows/ci-cd-demo.yml` runs when
changes are pushed to `main`. It runs two Ubuntu jobs in order: `job1` prints a
success message, then `job2` runs after `job1` succeeds.
