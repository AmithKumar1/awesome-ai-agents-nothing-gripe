# Contributing

Thanks for helping keep this list current — the agent ecosystem moves fast, and PRs are the only way this list stays honest.

## What makes a good entry

- **Notable**: a real product, framework, protocol, or benchmark with genuine usage or influence — not a weekend demo.
- **A verified official URL**: the project's own site, docs, or repository. Links must resolve for humans (not just bots).
- **A one-line description**: what it is and why it matters, in plain language.
- **No marketing metrics**: no star counts, ARR figures, "most popular", or vendor-reported benchmark scores unless independently verifiable. If a vendor claim is worth mentioning, label it as vendor-reported.
- **A status tag when it's not plain active**: `(beta)`, `(legacy)`, `(archived)`, `(deprecated)`, `(sunsetting)`, `(maintenance)`, or `acquired by X` — with the detail logged in [docs/status-changes.md](docs/status-changes.md).

## Checklist for a PR

1. Add the entry to the right section of `README.md`, keeping alphabetical-ish grouping sensible (sections are roughly ordered by prominence, not strictly alphabetical).
2. Add the matching object to `data/agents.json` with fields: `id` (slug), `name`, `url`, `github` (or `null`), `license` (or `null` — never guess), `status`, `categories` (array of section slugs), `description`.
3. If the entry changes a status (deprecation, acquisition, shutdown), update `docs/status-changes.md` too.
4. Make sure CI passes: JSON validation and the lychee link check run on every PR.

## Updating or removing entries

Entries that shut down, get acquired, or enter maintenance mode should be **updated, not deleted** — the status log is part of the list's value. Only remove entries that were never real (dead on arrival, renamed with a redirect in place).

## License of contributions

By contributing, you agree your contributions are released under the repository's [MIT License](LICENSE).
