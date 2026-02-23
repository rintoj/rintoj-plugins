# rintoj-plugins

A curated collection of Claude Code plugins for enhanced development workflows.

## Getting Started

### Add the Marketplace

Run this command in Claude Code to add this marketplace as a source:

```
/plugin add-source rintoj-plugins github:rintoj/rintoj-plugins
```

### Browse & Install

```
/plugin list rintoj-plugins     # See available plugins
/plugin install <name>@rintoj-plugins
```

---

## Available Plugins

### Planr

**End-to-end GitHub-based project management for Claude Code**

Transform how you manage software projects - from capturing an idea to deploying working code.

```
/plugin install planr@rintoj-plugins
```

#### What It Does

| Phase | Command | Result |
|-------|---------|--------|
| **Capture** | `/new-project` | Interactive Q&A creates `docs/project-brief.md` |
| **Plan** | `/plan-project` | AI generates architecture + implementation plan |
| **Sync** | `/sync-github` | Creates GitHub Milestones, Issues, Project Board |
| **Build** | `/implement-milestone 1` | Autonomous agents implement code with quality checks |
| **Track** | `/view-progress` | Real-time dashboard across local files + GitHub |

#### Key Features

- **Interactive Project Capture** - Guided Q&A builds comprehensive project briefs
- **Autonomous Planning** - AI generates architecture docs, ADRs, and task breakdowns
- **Feature-Based Vertical Slices** - Each sprint delivers a complete, testable feature
- **14 Specialized Agents** - Planning, implementation, review (4 focused sub-agents), testing, docs, research
- **Parallel Execution** - Independent tasks run simultaneously for faster builds
- **GitHub Integration** - Milestones, Issues, Project Boards, PRs auto-managed
- **Quality Gates** - Lint, build, test checks before every merge
- **Tech Stack Detection** - Auto-loads NestJS, Next.js, GraphQL patterns

#### Workflow

```
┌─────────────────────────────────────────────────────────────┐
│                    PROJECT LIFECYCLE                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  /new-project      → Capture requirements                   │
│        ↓                                                    │
│  /plan-project     → Architecture + implementation plan     │
│        ↓                                                    │
│  /sync-github      → GitHub Milestones + Issues + Board     │
│        ↓                                                    │
│  /implement-*      → Autonomous code implementation         │
│        ↓                                                    │
│  /review --fix     → AI review with auto-fix                │
│        ↓                                                    │
│  /view-progress    → Track completion status                │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

#### Quick Start

```bash
/forge help              # See all commands
/new-project             # Start capturing your idea
/plan-project            # Generate architecture + plan
/sync-github             # Push to GitHub
/implement-milestone 1   # Start building
```

#### Commands Overview

| Category | Commands |
|----------|----------|
| **Planning** | `/new-project`, `/plan-project`, `/generate-architecture`, `/generate-plan`, `/generate-features` |
| **GitHub** | `/sync-github`, `/update-status` |
| **Implementation** | `/implement-project`, `/implement-milestone`, `/implement-sprint`, `/implement-task` |
| **Review** | `/review`, `/review-pr`, `/review-task`, `/review-sprint`, `/review-milestone` |
| **Tracking** | `/view-progress`, `/view-milestone`, `/view-sprint`, `/view-task`, `/view-backlog` |
| **Issue Management** | `/capture-issue`, `/schedule-issue` |
| **Testing & Docs** | `/test`, `/test-generate`, `/docs-generate`, `/research` |
| **Git** | `/commit`, `/merge`, `/rollback` |
| **Utilities** | `/forge`, `/forge help`, `/init` |

#### Agents

| Agent | Purpose |
|-------|---------|
| **planning-agent** | Architecture + implementation plan generation |
| **features-agent** | Feature extraction with user stories |
| **task-agent** | Single task implementation |
| **milestone-agent** | Sprint orchestration with parallel execution |
| **project-agent** | Full project implementation |
| **review-orchestrator-agent** | Orchestrates focused review sub-agents |
| **review-code-agent** | Code quality & correctness review |
| **review-security-agent** | Security vulnerability review |
| **review-perf-agent** | Performance & best practices review |
| **review-design-agent** | Design compliance review (UI only) |
| **test-agent** | Test generation and fixing |
| **docs-agent** | Documentation generation |
| **research-agent** | Technical research and POCs |
| **schedule-agent** | Backlog issue scheduling |

#### Requirements

- **GitHub CLI (`gh`)** - [Install](https://cli.github.com/) and authenticate with `gh auth login`
- **Git** - Repository with remote configured
- **Node.js** - For lint/build/test commands

#### Learn More

Full documentation: [github.com/rintoj/planr](https://github.com/rintoj/planr)

---

### Designr

**Figma design workflow: setup, screen creation with auto-validation loop, and design validation**

Create production-quality screens with Design Thinking — automatically validated and iterated against your design system.

```
/plugin install designr@rintoj-plugins
```

#### What It Does

| Phase | Command | Result |
|-------|---------|--------|
| **Setup** | `/designr:setup` | First run: create design system; repeat runs: diff + reconcile |
| **Design** | `/designr:design` | Design a screen with auto-validate loop (up to 3 fix iterations) |
| **Validate** | `/designr:validate` | Validate the selected screen against design system standards |
| **Lint** | `/designr:lint` | Lint a frame and report all issues (no auto-fix) |

#### Key Features

- **Design Thinking** — 7-phase workflow: canvas study → aesthetic direction → content plan → build → fixups → verify → report
- **Auto-Validation Loop** — Screen is validated and redesigned if issues are found (up to 3 iterations)
- **Design System Setup** — Create and reconcile typography, colors, spacing, and radius tokens
- **Token Compliance** — Verifies all visual properties are bound to design system tokens
- **Standalone Validation** — Validate any screen with a screenshot + structural + token spot-check
- **Design Cohesion** — Analyzes existing screens and matches their aesthetic direction

#### Workflow

```
┌──────────────────────────────────────────────────────────────┐
│                    DESIGN WORKFLOW                           │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  /designr:setup     → Connect Figma + sync tokens            │
│        ↓                                                     │
│  /designr:design    → Design screen + auto-validate          │
│        ↓                                                     │
│  /designr:lint      → Quick lint report (no fix)               │
│        ↓                                                     │
│  /designr:validate  → Spot-check any screen                  │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

#### Quick Start

```bash
/designr:setup             # Connect Figma and sync design system (first run or re-sync)
/designr:design            # Design a screen with iterative validation
/designr:validate          # Validate the selected screen
```

#### Commands (4)

| Command | Description |
|---------|-------------|
| `/designr:setup` | First run: create design system from scratch; repeat: diff + fix tokens |
| `/designr:design` | Design a screen with iterative validation (up to 3 fix iterations) |
| `/designr:lint` | Lint the selected frame and report all issues (no auto-fix) |
| `/designr:validate` | Validate the selected Figma screen against design system standards |

#### Agents (2)

| Agent | Purpose |
|-------|---------|
| **screen-designer** | Creates distinctive Figma screens using Design Thinking (7-phase workflow) |
| **screen-validator** | Validates screens against design system; returns PASS or ISSUES_FOUND |

#### Skills (2)

| Skill | Purpose |
|-------|---------|
| **design-system** | Connect, diff, and reconcile Figma design system tokens against canonical file |
| **design-rules** | Universal design enforcement rules: token binding, auto-layout, typography, shadows, icons, accessibility |

#### Requirements

- **Claude Figma MCP** — WebSocket server running (`bun socket`)
- **Figma Plugin** — Claude MCP Plugin open in Figma

#### Learn More

Full documentation: [github.com/rintoj/designr](https://github.com/rintoj/designr)

---

### Design Cache

**Design knowledge base with semantic search for UI screenshots and web pages**

Ingest UI designs, analyze them with Claude Vision, and search/retrieve cached specs when building UIs.

```
/plugin install design-cache@rintoj-plugins
```

#### What It Does

| Phase | Command | Result |
|-------|---------|--------|
| **Setup** | `/design-cache:setup` | Configure MCP server and database |
| **Ingest** | `/design-cache:ingest` | Analyze a screenshot and cache its spec |
| **Ingest URL** | `/design-cache:ingest-url` | Load a web page, detect sections, ingest each |
| **Search** | `/design-cache:search` | Semantic search across cached designs |
| **Retrieve** | `/design-cache:get` | Get full spec with tokens, components, HTML snippets |
| **Browse** | `/design-cache:list` | List all cached designs |

#### Key Features

- **Claude Vision Analysis** - Extracts layout, components, tokens, and HTML snippets from screenshots
- **Semantic Search** - Find designs by natural language description using pgvector embeddings
- **Web Page Ingestion** - Puppeteer-based section detection and individual screenshots
- **Structured Specs** - Design tokens, component styles, Tailwind snippets, responsive notes
- **MCP Integration** - Tools available directly to Claude Code for design-informed UI building

#### Requirements

- **Docker** - For PostgreSQL + pgvector
- **Anthropic API Key** - For Claude Vision analysis
- **Embedding API Key** - Voyage AI (recommended), OpenAI, or local fallback

#### Learn More

Full documentation: [github.com/rintoj/design-cache-mcp](https://github.com/rintoj/design-cache-mcp)

---

## Contributing

Have a plugin idea? Open an issue at [github.com/rintoj/rintoj-plugins](https://github.com/rintoj/rintoj-plugins).

## License

MIT
