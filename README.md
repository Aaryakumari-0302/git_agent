# Daily Git Agent

A small GitHub Actions workflow that records one clearly labeled automated daily heartbeat in `activity-log.md`.

## Automation

- Runs daily at **5:00 pm India Standard Time** (03:30 UTC).
- Can also be started manually from the **Actions** tab using **Run workflow**.
- Uses the repository-scoped `GITHUB_TOKEN`; no personal access token is needed.
- Writes one dated entry to `activity-log.md` and commits it.
- Avoids creating a second heartbeat if the workflow is rerun on the same IST date.

## Optional: attribute commits to your contribution graph

By default, commits are authored by `github-actions[bot]`. If you want them attributed to your GitHub contribution graph, add a repository Actions secret named `COMMIT_EMAIL` containing an email address verified on your GitHub account (your GitHub-provided noreply address is suitable).

To add it:
1. Open **Settings → Secrets and variables → Actions**.
2. Select **New repository secret**.
3. Set the name to `COMMIT_EMAIL` and the value to your verified GitHub email or noreply address.

## Install

1. Download and extract this ZIP.
2. In your `git_agent` repository, choose **Add file → Upload files**.
3. Upload `README.md` and the `.github` folder from this package, then commit the upload to the `main` branch.
4. Open **Actions** and enable workflows if GitHub prompts you.
5. Open **Daily Git Agent** and choose **Run workflow** to test it.

The scheduled workflow runs on the repository's default branch. This is an automated heartbeat commit, not a claim that new project code was developed each day.
