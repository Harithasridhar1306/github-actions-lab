# GitHub Actions Cheatsheet

## Workflow skeleton

```yaml
name: CI

on:
  push:
    branches: [main]

permissions:
  contents: read

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm test
```

## Triggers

| Need | Syntax |
|---|---|
| Push | `on: push` |
| Pull request | `on: pull_request` |
| Manual | `workflow_dispatch` |
| Schedule | `schedule` + cron |
| Reusable workflow | `workflow_call` |

## Jobs

```yaml
jobs:
  test:
    runs-on: ubuntu-latest

  deploy:
    needs: test
```

`needs` references **job IDs**, not step names.

## Conditions

```yaml
if: github.ref == 'refs/heads/main'
if: success()
if: failure()
if: always()
```

## Matrix

```yaml
strategy:
  matrix:
    node: [20, 22]
```

## Variables and secrets

```yaml
env:
  APP_ENV: production

run: echo "$APP_ENV"
run: echo "${{ secrets.API_KEY }}"
```

## Outputs

Use step outputs to pass values within a job and job outputs to pass values between jobs.

## Artifacts

Use `actions/upload-artifact` to persist build output between jobs or after a run.

## Caching

Use `actions/cache` or an action with built-in caching to avoid repeatedly downloading dependencies.

## Security

Start with least privilege:

```yaml
permissions:
  contents: read
```

Grant additional permissions only when a job needs them. For cloud authentication, prefer short-lived OIDC federation over long-lived static credentials where the cloud provider and workload design support it.

## Production checklist

- [ ] Explicit `permissions`
- [ ] Dependencies use appropriate version pinning policy
- [ ] Secrets are not printed
- [ ] Deployments use protected environments where appropriate
- [ ] Concurrency is considered for deployments
- [ ] Build artifacts are traceable
- [ ] Failure paths are observable
- [ ] Reusable logic is shared instead of duplicated
