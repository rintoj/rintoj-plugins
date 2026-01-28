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
- **10 Specialized Agents** - Planning, implementation, review, testing, docs, research
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
| **review-agent** | Code review with auto-fix |
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

## Contributing

Have a plugin idea? Open an issue at [github.com/rintoj/rintoj-plugins](https://github.com/rintoj/rintoj-plugins).

## License

MIT
