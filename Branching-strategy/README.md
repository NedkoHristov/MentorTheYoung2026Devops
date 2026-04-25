# Branching Strategy

## Strategy

For this project, I would use **trunk-based development with release branches**.

This is simple and fits the requirements. The team needs daily deploys, a stable 72h QA window, and the ability to hotfix production without shipping unfinished work from staging.

The main idea:

- `main` is always stable
- developers work on short-lived branches (`feature/*`)
- `release/*` branches are long-lived for the duration of the 72h QA window
- every change goes through a Pull Request and GitHub Actions must pass
- production deploys from `main`
- staging deploys from `release/*`
- hotfixes branch from `main`, not from `release/*`

---

## Branches

### `main`

Long-lived. Always stable and deployable to production.

### `release/*`

Long-lived for 72 hours. Cut from `main` when a big release is ready for QA. Nothing new merges into it during the QA window.

### `feature/*`

Short-lived. Branched from `main`, merged back via Pull Request.

### `hotfix/*`

Short-lived. Branched from `main`, merged back via Pull Request. 

---

## Fixing a production bug while a release is in staging

```text
1. git checkout -b hotfix/checkout-bug main
2. fix the bug, commit
3. open PR into main -> review + GitHub Actions must pass
4. merge into main -> deploys to production
```
