# Contributing to Design Orchestra

Thank you for your interest in improving Design Orchestra! This guide covers
everything you need to get started.

## Prerequisites

- **Node.js 20** or newer
- **npm** (comes with Node.js)

## Setup

```bash
git clone https://github.com/Dheerajjha451/design-orchestra.git
cd design-orchestra
npm install
```

## Development workflow

```bash
npm run build        # Compile TypeScript → dist/
npm test             # Build + run all tests
npm run validate     # Build + run package validation checks
npm run pack:check   # Preview what npm publish would include
```

Always run `npm test` before submitting a pull request. The CI matrix runs
tests on Ubuntu, macOS, and Windows across Node 20, 22, and 24.

## Project structure

| Path | Purpose |
|---|---|
| `src/core.ts` | Library entry point — direction generation, validators, moodboard renderer |
| `src/cli.ts` | CLI commands: init, update, doctor, validate, uninstall, concepts |
| `src/types.ts` | Shared TypeScript interfaces |
| `src/data/` | Agent definitions, archetypes, and design knowledge |
| `src/test/` | Node.js test runner tests |
| `templates/skills/` | Portable skill markdown files installed into user projects |

## Adding or improving skills

1. Add or edit a skill under `templates/skills/<skill-name>/SKILL.md`.
2. Every skill file must start with valid YAML frontmatter containing `name`
   and `description`.
3. The `validate` command checks that exactly seven skill files exist with
   correct frontmatter — update the count in `cli.ts` if you add a new skill.

## Adding or improving agents

Agent definitions live in `src/data/agents.ts`. Each agent has a name,
description, sandbox mode, and instructions string. The `validate` command
checks that exactly six agents exist.

## Pull request checklist

- [ ] `npm test` passes locally
- [ ] `npm run validate` passes locally
- [ ] New features include corresponding tests
- [ ] Commit messages are clear and descriptive
- [ ] No unrelated formatting changes

## Code style

- TypeScript strict mode is enabled
- Prefer `const` over `let`; avoid `var`
- Use explicit return types on exported functions
- Keep lines reasonable in length; the project does not enforce a hard limit

## Reporting issues

Open a GitHub issue with:
- Steps to reproduce
- Expected vs actual behavior
- Node.js version and operating system
