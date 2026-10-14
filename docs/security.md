# Repository security configuration

## Branch protection

- Default branch: `main`
- One approving review required
- Stale reviews are dismissed
- Strict status checks are required
- Protection is enforced for administrators
- Force pushes and branch deletion are blocked

## CI

CI currently validates repository contents and blocks secret-style environment files from being committed.

When application code is added, CI must also run:

- dependency installation
- type checking
- unit tests
- integration tests
- Docker build

## Dependencies

Dependabot updates GitHub Actions weekly.

After the application baseline is imported, add dependency ecosystems to `.github/dependabot.yml`.

## GitHub Actions

Actions are restricted to selected actions. Allowed repositories:

- `actions/checkout`

Add new actions only after reviewing their source, permissions, and release integrity.

## Secret scanning

- Secret scanning is enabled.
- Secret scanning push protection is enabled.
