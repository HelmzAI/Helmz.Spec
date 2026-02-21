# Contributing to Helmz.Spec

## Branch Workflow

1. **Always work in a PR branch** — never commit directly to `main`.
2. Create a feature branch from `main`:
   ```bash
   git checkout main
   git pull origin main
   git checkout -b <type>/<short-description>
   ```
3. Push your branch and open a Pull Request.
4. All changes must be reviewed and merged via PR.

## Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/).

Format:
```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types

| Type | Description |
|------|-------------|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only changes |
| `style` | Code style changes (formatting, no logic change) |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `chore` | Other changes that don't modify proto files |

### Scopes

| Scope | Description |
|-------|-------------|
| `daemon` | DaemonService proto definitions |
| `relay` | RelayService proto definitions |
| `types` | Shared message types |
| `buf` | Buf configuration and code generation |

### Examples

```
feat(daemon): add StreamOutput server streaming RPC
fix(types): correct OutputType enum numbering
refactor(relay): rename TunnelMessage payload field
docs: update proto field comments
```

## Proto Guidelines

- Follow the [Buf style guide](https://buf.build/docs/best-practices/style-guide/)
- All enums must have an `UNSPECIFIED = 0` value
- Use `google.protobuf.Timestamp` for time fields
- Package: `helmz.v1`
- C# namespace: `Helmz.Spec.V1`

## Merging

- **Always squash merge** PRs into `main`.
- The squash commit message must follow conventional commit format.
- **Always delete the branch** after merging.
