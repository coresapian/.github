# Contributing to coresapian inc.

Thanks for your interest in contributing. This guide covers the basics for all repos under the coresapian organization.

## Quick Links

- [How to Contribute](#how-to-contribute)
- [Code Style](#code-style)
- [Commit Messages](#commit-messages)
- [Pull Request Requirements](#pull-request-requirements)
- [Reporting Issues](#reporting-issues)

---

## How to Contribute

We use a **fork + pull request** workflow:

1. **Fork** the repository you want to contribute to.
2. **Clone** your fork locally.
   ```bash
   git clone https://github.com/<your-username>/<repo>.git
   cd <repo>
   ```
3. **Create a branch** from `main` (or the repo's default branch).
   ```bash
   git checkout -b feat/my-new-feature
   ```
4. **Make your changes.** Keep PRs focused — one concern per branch.
5. **Push** to your fork.
   ```bash
   git push origin feat/my-new-feature
   ```
6. **Open a Pull Request** against the upstream repo's default branch. Fill in the PR template completely.

### Syncing Your Fork

Keep your fork up to date before starting new work:

```bash
git remote add upstream https://github.com/coresapian/<repo>.git
git fetch upstream
git checkout main
git merge upstream/main
```

---

## Code Style

Consistency matters. Run formatters and linters **before** committing.

### Python (autobuild, Njorun API, starpark, VisionVend)

- **Formatter & linter:** [ruff](https://docs.astral.sh/ruff/)
- **Line length:** 120
- **Python version:** target the minimum version specified in each repo's `pyproject.toml`

```bash
pip install ruff
ruff check .          # lint
ruff format .         # format
```

### TypeScript / JavaScript (Billboard-AI, syntheticmates, video-valhalla, Lonnrune, daviddelaurier, Njorun frontend)

- **Formatter:** [Prettier](https://prettier.io/)
- **Linter:** [ESLint](https://eslint.org/)
- **Config:** each repo ships its own — use what's there, don't introduce new rules unilaterally.

```bash
npx prettier --write .
npx eslint .
```

### Swift (Njorun macOS app, VisionVend iOS)

- **Formatter:** [swift-format](https://github.com/apple/swift-format)
- Run against the repo's `.swift-format` config if one exists; otherwise use Apple defaults.

```bash
swift-format format -i -r Sources/
swift-format lint -r Sources/
```

### Godot / GDScript (coresapian.com)

- Follow the [GDScript style guide](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_styleguide.html).
- Use the built-in script editor formatter before committing.

---

## Commit Messages

We use **[Conventional Commits](https://www.conventionalcommits.org/)**:

```
<type>(<scope>): <short summary>

<optional body>
<optional footer>
```

### Types

| Type | Use for |
|---|---|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, whitespace (no logic change) |
| `refactor` | Code restructuring without behavior change |
| `test` | Adding or updating tests |
| `chore` | Build, CI, tooling, dependencies |
| `perf` | Performance improvement |

### Examples

```
feat(ingestion): add parquet output support
fix(api): handle missing auth header gracefully
docs(readme): update setup instructions
chore(deps): bump fastapi to 0.115
```

- Use the **imperative mood** ("add feature" not "added feature").
- Keep the summary under **72 characters**.

---

## Pull Request Requirements

Every PR must meet these criteria before merge:

1. **Description** — Explain *what* changed and *why*. Reference related issues (`Closes #12`, `Relates to #8`).
2. **Tests** — New behavior must include tests. Bug fixes should include a regression test.
3. **Lint passes** — All formatters and linters must pass with zero errors. Warnings should be resolved or explicitly acknowledged.
4. **Clean history** — Squash or rebase if your branch has noisy merge commits. We prefer a clean, readable log.
5. **No secrets** — Never commit API keys, tokens, or credentials. Use environment variables.

### PR Title

Use the same conventional commit format:

```
feat(auth): add OAuth2 login flow
```

---

## Reporting Issues

Good bug reports get fixed faster. When opening an issue:

1. **Search first** — check for duplicates.
2. **Use a clear title** — summarize the problem in one sentence.
3. **Include details:**
   - Steps to reproduce
   - Expected vs. actual behavior
   - Relevant environment info (OS, Python/Node/Swift version, browser)
   - Logs, screenshots, or stack traces if available

### Feature Requests

Describe the use case, not just the solution. Explain *why* the feature matters and *who* it helps. Concrete examples beat vague ideas.

### Security Vulnerabilities

**Do not file public issues for security bugs.** Email security@coresapian.com instead.

---

## Questions?

Open a Discussion on the relevant repo, or reach out to the team directly. Welcome aboard.
