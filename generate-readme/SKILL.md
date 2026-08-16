---
name: generate-readme
description: Generate or update README.md and docs/ documentation for a project. Use when writing or revising the root README, a package-level README, or any file inside docs/. Applies Jay-1409 modular documentation standards.
---

# Generate README

## README.md structure

The root `README.md` must always contain these sections in this order:

1. **Title** — the project name as the `h1`.
2. **Tagline** — a brief italicized blockquote explaining the project's purpose. No jargon.
3. **Badges** — metadata shields: license, version, primary language.
4. **What's in it for you** — three to five bullet points describing end-user benefits. No internal architecture terms (no queues, threads, pools, hooks, components).
5. **Features** — a tight list focused on product capability. Do not describe implementation choices.
6. **Quick Start** — copy-pasteable install, start, and sample usage instructions.
7. **Documentation links** — relative links to files inside `docs/`. Never use absolute `file:///` URLs.
8. **License** — name and link to the `LICENSE` file.

## docs/ structure

Separate detailed content into focused files:

| File | Contents |
|------|----------|
| `docs/architecture.md` | Core modules, layer responsibilities, data flow, concurrency model. Link to diagrams. |
| `docs/api.md` | Every HTTP endpoint: method, path, request format, parameters table, example request, success and error responses. |
| `docs/contributing.md` | Setup, branch conventions, testing commands, PR checklist. |
| `docs/benchmarking.md` | A guide on how to benchmark the project if benchmarking scripts exists. |

Create only the files that are relevant to the current scope. Do not create placeholder files.

## Writing rules

- Write for the reader who has never seen this codebase.
- Use the imperative mood for steps ("Run `npm test`", not "You should run `npm test`").
- Keep sentences short. Prefer one idea per sentence.
- Use code blocks for every command, file path, and code snippet.
- All local file links must be relative (e.g., `./docs/api.md`).
- Do not copy internal code comments verbatim into documentation.

## Completion gate

Before handing off documentation:

1. Confirm every link in the README resolves to an existing file.
2. Confirm every command in Quick Start runs without error.
3. Run a spell-check pass on the finished document.
