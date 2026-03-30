# Claude Commands

A collection of custom slash commands (skills) for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). Each `.md` file is a reusable skill that adds a specialized workflow to your CLI.

> **Note :** All skills respond in French by default.

## Skills

| Command | Description | Model |
|---------|-------------|-------|
| `/instruction` | Guide interactif pour créer un prompt XML structuré | default |
| `/audit` | Audit qualité d'un skill — checklist 13 critères + plan d'amélioration | default |
| `/browse` | QA visuel — explorer et tester une app via Playwright | opus |
| `/plan-ceo-review` | CEO review — challenge l'idée produit avant de coder | opus |
| `/plan-eng-review` | Lead engineer — verrouiller l'architecture avant de coder | opus |
| `/review` | Code review paranoïaque — trouver les bugs avant la prod | sonnet |
| `/retro` | Rétro — analyser la productivité sur une période donnée | sonnet |
| `/ship` | Release manager — tests, commit, push et PR en une commande | sonnet |

## Details

### `/instruction`

Interactive prompt engineering guide. Asks targeted questions to build a structured XML prompt with up to 6 sections (`role`, `context`, `donnees`, `instructions`, `format_sortie`, `contraintes`), adapted to the request complexity (simple/moyenne/complexe).

```
/instruction
```

### `/audit`

Evaluates any skill against a 13-criteria quality checklist (structure, precision, robustness, conciseness). Produces a scored report, improvement plan, and a corrected version of the skill ready to copy.

```
/audit <paste your skill here>
```

### `/browse`

Visual QA tester using Playwright MCP. Navigates a web app, takes screenshots, checks responsive layouts, console errors, and produces a severity-ranked findings report. Requires Playwright MCP tools.

```
/browse http://localhost:3000
```

### `/plan-ceo-review`

Acts as a demanding CEO to challenge a product idea before any code is written. Questions the target user, the problem, existing alternatives, MVP scope, and kill signals. Returns a GO / NO-GO / PIVOT verdict.

```
/plan-ceo-review "Add a notification system for late invoices"
```

### `/plan-eng-review`

Senior lead engineer that scans the codebase and designs the architecture for a validated feature. Outputs a technical plan covering data model, APIs, edge cases, test plan, and implementation order.

```
/plan-eng-review "Add a notification system for late invoices"
```

### `/review`

Paranoid code reviewer that assumes every change contains at least one bug. Runs a systematic review (logic, security, race conditions, edge cases, performance) and returns a severity-ranked report.

```
/review staged
/review HEAD~3
/review src/api/handler.ts
```

### `/retro`

Productivity analyst that examines git history for a given period. Categorizes commits, detects hot spots and anti-patterns, and produces a retrospective with key metrics and one actionable recommendation.

```
/retro today
/retro week
/retro 2025-01-01..2025-01-31
```

### `/ship`

Release manager that handles the full shipping flow: pre-flight checks (no secrets, not on main), runs tests, creates a conventional commit, pushes, and opens a PR.

```
/ship "Add invoice notifications"
```

## Installation

Copy the `.md` files you want into your Claude Code commands directory:

```bash
# Project-level (recommended)
cp *.md .claude/commands/

# User-level (available in all projects)
cp *.md ~/.claude/commands/
```

Then use them in Claude Code with `/command-name`.
