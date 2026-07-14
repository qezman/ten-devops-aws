# Day 3 - Task 1: CI/CD Setup with GitHub Actions

## Objective

Design a pipeline to auto-test and build the Docker image on every push.

## Workflow

File: `.github/workflows/docker-build.yml` (in static-site-docker repo)

Triggers on push/PR to main. Steps:

1. Checkout code
2. Build Docker image (`docker build -t static-site-docker .`)
3. Smoke test: run container, wait for boot, curl with `--fail`, exit 1 on failure
4. Stop test container

## Verification

Confirmed via GitHub Actions tab - build and test steps both passed.

## Screenshots

See `/screenshots` folder.

## Key Takeaway

CI pipelines run on GitHub-hosted runners, fully independent of any cloud
infrastructure - this validates the Docker image without needing the EC2
instance to be running.
