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

**Complete Figma design workflow: setup, sketch, create, replicate, review, polish, sync, components**

Transform Figma designs into production-ready screens with token compliance and bi-directional sync.

```
/plugin install designr@rintoj-plugins
```

#### What It Does

| Phase | Command | Result |
|-------|---------|--------|
| **Setup** | `/designr:setup` | Verify Figma connection & sync design system |
| **Sketch** | `/designr:sketch` | Generate screen specs from features |
| **Create** | `/designr:create` | Create screens (3 variants) with token binding |
| **Replicate** | `/designr:replicate` | Replicate design screenshots into Figma |
| **Review** | `/designr:review` | Validate flows, states, requirements coverage |
| **Polish** | `/designr:polish` | Full pipeline: visual polish + token binding + audit |
| **Sync** | `/designr:sync` | Bi-directional Figma ↔ figma-map.md sync |

#### Key Features

- **3-Variant Screen Creation** - Every screen created in 3 variants (consistency, layout variation, visual variation)
- **Design Derivation** - Extend existing screens with `--extend` flag to create variants
- **Design Replication** - Convert screenshots into editable Figma layouts with full color/layout extraction
- **Polish Pipeline** - 3-phase: visual polish → token mapping → compliance audit
- **Design System Sync** - Create and reconcile typography, colors, spacing tokens
- **Token Compliance** - Auto-bind design tokens and generate compliance reports
- **Flow Validation** - Verify user flows and system state coverage
- **Bi-directional Sync** - Sync screens and feature annotations between Figma and figma-map.md
- **Planr Integration** - Reads project-brief.md, feature definitions, and figma-map.md

#### Workflow

```
┌──────────────────────────────────────────────────────────────┐
│                   DESIGN WORKFLOW (v4.0.0)                   │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  /designr:setup          → Verify connection + sync tokens   │
│        ↓                                                     │
│  /designr:sketch         → Generate screen specs             │
│        ├─ Create new screens: /designr:create               │
│        └─ Replicate screenshots: /designr:replicate         │
│        ↓                                                     │
│  /designr:sync           → Bi-directional sync               │
│        ↓                                                     │
│  /designr:review         → Validate flows & states           │
│        ↓                                                     │
│  /designr:polish         → Polish + tokens + compliance      │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

#### Quick Start

```bash
/designr                   # See all commands and workflow
/designr:setup             # Verify Figma and sync design system
/designr:sketch            # Generate screen specs
/designr:create            # Create screens with 3 variants
/designr:polish            # Full polish pipeline
```

#### Commands Overview (9)

| Category | Commands |
|----------|----------|
| **Setup & Sketch** | `/designr:setup`, `/designr:sketch` |
| **Creation & Replication** | `/designr:create`, `/designr:replicate` |
| **Review & Polish** | `/designr:review`, `/designr:polish` |
| **Sync & Utilities** | `/designr:sync`, `/designr:components`, `/designr` |

#### Agents (11)

| Agent | Purpose |
|-------|---------|
| **screen-sketcher** | Generates screen specs from feature definitions |
| **screen-creator** | Creates screens from requirements (supports 3 variants) |
| **screen-deriver** | Derives new screens from existing selections with --extend |
| **design-replicator** | Replicates design screenshots into editable Figma layouts |
| **design-validator** | Validates flows and system state coverage |
| **design-polisher** | Polishes designs to production quality |
| **design-mapper** | Maps and binds design tokens to components |
| **design-auditor** | Audits token compliance and generates reports |
| **token-reconciler** | Sets up and reconciles design system tokens |
| **token-catalog-builder** | Builds token catalogs from design systems (utility) |
| **doc-discoverer** | Discovers and parses project documentation (utility) |

#### Requirements

- **Claude Figma MCP** - WebSocket server for Figma connection
- **Figma Plugin** - Claude MCP Plugin installed in Figma

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
