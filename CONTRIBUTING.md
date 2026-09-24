# Contributing Guide

This guide covers how NexusPulse works in its own repositories and in client repositories where @NexusPulseTech contributes.
If a client repository has its own contributing rules, **the client's rules apply**.

## 1. Access

- NexusPulse is added to client repositories as a collaborator with **write** access. Admin access stays with the repository owner.
- Access is granted per repository, never to a whole organization by default.
- When an engagement ends, the owner removes our access. We do not keep copies of private client code.

## 2. Commit identity

All work done for NexusPulse is committed under one identity so the history stays consistent:

```bash
git config user.name  "NexusPulseTech"
git config user.email "238037559+NexusPulseTech@users.noreply.github.com"
```

- Set this **per repository** (without `--global`) so personal projects keep their own identity.
- Use the GitHub no-reply address above. Personal email addresses are never used in company commits.

## 3. Branches

`main` is protected and only receives changes through pull requests.

| Prefix | Use for |
| --- | --- |
| `feat/` | New features |
| `fix/` | Bug fixes |
| `refactor/` | Code changes that do not change behavior |
| `docs/` | Documentation only |
| `chore/` | Tooling, dependencies, configuration |
| `ci/` | CI/CD pipelines and deploy scripts |

Examples: `feat/quest-verification`, `fix/login-redirect`.

## 4. Commit messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<optional scope>): <short summary in the imperative>

<optional body: what changed and why>
```

Allowed types: `feat`, `fix`, `refactor`, `perf`, `docs`, `style`, `test`, `chore`, `ci`, `build`.

Examples:

```
feat(api): add idempotency key to point transactions
fix(auth): keep wallet session after page reload
docs(architecture): update ERD for campaign tables
```

Keep the message about the change itself. Do not add signatures, links or footers.

## 5. Pull requests

- Keep pull requests small and focused on one change.
- The description says **what** changed, **why**, and **how it was tested**.
- CI must pass before review.
- The repository owner, or a reviewer they choose, approves and merges. NexusPulse does not merge its own pull requests into a client's `main` unless the client asks us to.

## 6. Secrets and confidentiality

- Never commit `.env` files, API keys, private keys or credentials. Use the repository's secret store, for example GitHub Actions secrets.
- If a secret is committed by mistake, tell the owner right away and rotate it. Removing the commit is not enough.
- Client projects are confidential. We do not name them, share their code or show screenshots publicly without written permission.

## 7. Contributing to this repository

This repository holds NexusPulse's public company information.
To suggest a change, open an issue or a pull request against `main`.
