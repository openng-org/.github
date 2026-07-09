# Contributing to OpenNG libraries

Thank you for your interest in contributing to [OpenNG](https://www.openng.org/) open-source Angular libraries. This guide describes how to report issues, propose changes, and submit pull requests. Individual repositories may add project-specific notes in their README — read those first when they exist.

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you agree to uphold it. Unacceptable behavior can be reported to the project maintainers.

## AI Policy

We require all contributors to follow our [AI Policy](https://www.openng.org/contribute/ai-policy) when contributing to this repository. This policy is in place to ensure code quality, maintainer sanity, and a healthy community culture.

## Ways to contribute

You do not need to write code to help:

- **Report bugs** with a minimal reproduction (StackBlitz or a small GitHub repo).
- **Suggest features** and describe the problem you are trying to solve.
- **Improve documentation** — typos, missing examples, and outdated API references are valuable fixes.
- **Review pull requests** and help triage issues.
- **Answer questions** in issues and discussions.

Use the issue templates when opening a new issue. They ask for the Angular, Node, and library versions we need to investigate problems quickly.

## Before you start

1. **Search existing issues** to avoid duplicates.
2. **Read the README and docs** for the library you are working on.
3. **Open an issue first** for large features or API changes so maintainers can agree on direction before you invest significant time.
4. **Ask questions early** if requirements or scope are unclear.

For security vulnerabilities, do **not** open a public issue. Use the private disclosure channel described in the [repository's security policy](./SECURITY.md).

## Development setup

### Prerequisites

Check the target repository's README and `package.json` for exact versions. Typical requirements:

| Tool | Notes |
|------|-------|
| **Node.js** | Active LTS (see the repo's `engines` field or `.nvmrc`) |
| **Package manager** | npm, pnpm, or yarn — use the one the project documents |

### Getting the code running

```bash
git clone https://github.com/openng-org/<repo>.git
cd <repo>
npm install          # or pnpm install / yarn
npm run build        # build the library(ies)
npm test             # run unit tests
npm run lint         # lint (if configured)
```

Many libraries include a **demo app** or **playground** project for manual testing:

```bash
npm start            # often: ng serve <demo-project>
```

Refer to the repository's `package.json` scripts and README for the exact commands.

### Typical workspace layout

```
projects/
  <library-name>/     # publishable Angular library
    src/
      lib/
      public-api.ts   # exported surface — treat changes here as public API
  <demo-app>/         # local dev / integration testing (not published)
```

Changes to `public-api.ts` and exported types are **public API changes** and may require semver consideration and documentation updates.

## Making changes

### Branch from the default branch

Create a focused branch from `main` (or the branch the repo documents):

```bash
git checkout -b fix/issue-123-description
# or
git checkout -b feat/short-feature-name
```

Keep pull requests small and scoped to one logical change when possible.

### Angular library guidelines

<!-- To be filled with Agent Skills excerpt -->

### Tests

All behavioral changes should include tests:

Run the full test suite locally before opening a pull request:

```bash
npm test
npm run test -- --watch=false   # CI-style single run, if supported
```

Fix lint and type errors:

```bash
npm run lint
```

### Documentation

Update documentation alongside code changes:

- README usage examples for new or changed APIs.
- Migration notes for deprecations and breaking changes.

Documentation-only pull requests are welcome and do not require an issue first.

## Submitting a pull request

1. **Fill out the PR template** if the repository provides one.
2. **Link related issues** (`Fixes #123` or `Closes #123`).
3. **Describe what changed and why** — include before/after behavior for bug fixes.
4. **Note breaking changes** explicitly in the PR description.
5. **Confirm tests pass** and add tests for new behavior.
6. **Update the CHANGELOG** if the repository maintains one and your change is user-facing.

Maintainers may request changes, squash commits, or rebase before merge. Be responsive to review feedback.

### Pull request checklist

- [ ] Issue discussed or bug clearly described (link issue when applicable)
- [ ] Tests added or updated
- [ ] Documentation updated
- [ ] `npm run build`, `npm test`, and `npm run lint` pass locally
- [ ] Public API changes documented; breaking changes called out
- [ ] Commit messages follow [Conventional Commits](#commit-messages)
- [ ] Code of Conduct upheld

## Commit messages

Use [Conventional Commits](https://www.conventionalcommits.org/) so changelogs and semver releases stay predictable:

```
<type>(<scope>): <short description>

[optional body]

[optional footer(s)]
```

Common types:

| Type | Use for |
|------|---------|
| `feat` | New feature (minor semver bump) |
| `fix` | Bug fix (patch semver bump) |
| `docs` | Documentation only |
| `test` | Adding or correcting tests |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `perf` | Performance improvement |
| `chore` | Tooling, CI, dependencies |
| `build` | Build system or packaging changes |

Examples:

```
feat(button): add size input for sm, md, and lg variants
fix(http): retry failed requests when offline status changes
docs(readme): document standalone provideFeature setup
```

Use `BREAKING CHANGE:` in the footer (or `feat!:` / `fix!:`) for changes that require a major version bump:

```
feat(api)!: rename provideLegacyFeature to provideFeature

BREAKING CHANGE: provideLegacyFeature has been removed. Use provideFeature instead.
```

Scope should match the library or package name when the workspace contains multiple projects (for example, `feat(data-table): ...`).

## Versioning and releases

OpenNG libraries follow [Semantic Versioning](https://semver.org/):

- **MAJOR** — incompatible public API changes
- **MINOR** — backward-compatible functionality
- **PATCH** — backward-compatible bug fixes

Release mechanics (automation, tagging, npm publish) are maintainer responsibilities and vary by repository. Contributors do not need to bump version numbers unless the PR template or maintainers ask you to update the CHANGELOG.

## Reporting bugs effectively

Good bug reports save everyone time. Include:

- **Minimal reproduction** — a StackBlitz or small repo that demonstrates the issue without unrelated code
- **Library, Angular, and Node versions**
- **Package manager** and browser(s) affected
- **Standalone vs NgModule** setup, and whether **SSR** or **zoneless** change detection is involved
- **Expected vs actual behavior**
- **Console errors or stack traces**

Issues without enough information to reproduce may be closed with a request for more details.

## Getting help

- [OpenNG website](https://www.openng.org/)
- Repository README and documentation
- GitHub Issues and Discussions (when enabled on the repo)

Thank you for helping improve Angular open source for the community.
