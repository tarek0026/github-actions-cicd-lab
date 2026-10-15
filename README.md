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

Start a feature from the integration branch and merge it back when it is ready:

```sh
git switch develop
git switch -c feature/lab-content
# Make and commit the feature change
git switch develop
git merge --no-ff feature/lab-content
git switch main
git merge --no-ff develop
```

The page includes a project-status section to show that feature work has been
integrated into `develop`.

## CI/CD workflow

The GitHub Actions workflow at `.github/workflows/ci-cd-demo.yml` runs when
changes are pushed to `main`. It runs two Ubuntu jobs in order: `job1` prints a
success message, then `job2` runs after `job1` succeeds.
