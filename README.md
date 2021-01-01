# SigNoz

## Source development guide

### Product and architecture

Observability for traces, metrics and logs, with queries, dashboards and alerts.

Go services in `cmd/` and `pkg/` expose the query and management APIs; React/TypeScript frontend in `frontend/` renders telemetry visualizations. Deployment resources under `deploy/` configure the telemetry storage and collection stack.

### Requirements and local development

Go version from `go.mod`; Node >=22 and pnpm >=10 <11 for the frontend; Docker for a complete telemetry stack.

Run these commands from the repository root unless a `cd` is shown:

```sh
cd frontend
pnpm install
pnpm dev
```

These are source-defined entry points. Full dependency installation and service startup were not run during the portfolio maintenance audit; successful application deployment is not claimed.

### Environment configuration

Inspect `frontend/example.env` and the component-specific environment templates before startup. Supply local database, service URLs and integration credentials through untracked environment files or a secret manager. Do not copy production credentials into tracked files.

### Testing

```sh
cd frontend
pnpm test
```

The full application suite requires the dependencies and services described above. Source paths and documented script names were inspected, and `git diff --check` passed. Application tests and builds were not executed.

### Deployment and integrations

Start with `deploy` and review image versions, persistent data paths, authentication, exposed ports and backups before production use. Integration implementations and configuration are in the source directories described above; generated API clients must stay in sync with server contracts.

### Source provenance and license

Imported from [SigNoz/signoz](https://github.com/SigNoz/signoz); upstream functionality and copyright belong to the original contributors. Local Git history begins with a 2026 source snapshot import, not historical authorship. The exact imported upstream revision is unknown. The upstream GitHub repository was created on 2021-01-03; the local year directory is organizational metadata.

Read [LICENSE](LICENSE) and nested license/notice files before redistribution; enterprise and bundled third-party components may use different terms. Restored root license text was retrieved verbatim from the official upstream repository during this maintenance pass.

## Distribution status

Further publication of this complete imported snapshot is on hold: `ee/LICENSE` restricts redistribution of enterprise code. The existing remote import was not deleted or rewritten. Resolve permission or obtain a correctly scoped community source tree before publishing additional history. Root community licensing does not override enterprise terms.
