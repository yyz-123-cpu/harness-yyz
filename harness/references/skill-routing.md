# Harness Skill Routing Reference

This file documents the skill routing system in the Harness ecosystem.

## Routing Rules

1. **1% rule**: If there's even a 1% chance a skill applies, invoke it
2. **Process before implementation**: brainstorming before coding, systematic-debugging before fixing
3. **Domain skills after process skills**: frontend-design after brainstorming, nature-writing after research
4. **User instructions override skills**: If CLAUDE.md says "don't use TDD" and TDD skill says "always use TDD," follow CLAUDE.md

## Core Process Skills (invoke FIRST)

| Skill | Trigger | Type |
|-------|---------|------|
| `brainstorming` | ANY creative work, new feature, component, behavior change | Rigid |
| `systematic-debugging` | ANY bug, test failure, unexpected behavior | Rigid |
| `test-driven-development` | New feature, bugfix, refactoring, behavior change | Rigid |
| `planning-with-files` | Multi-step task (5+ tool calls) | Flexible |
| `writing-plans` | Spec exists, need implementation plan | Flexible |

## Code Quality

| Skill | Trigger |
|-------|---------|
| `code-review-excellence` | Reviewing PRs, establishing review standards |
| `requesting-code-review` | Task complete, major feature done, before merge |
| `simplify` | Refactoring, code quality improvement |

## Git & Project Management

| Skill | Trigger |
|-------|---------|
| `git-commit` | Creating commits, writing commit messages |
| `harness` | Harness init/status/update |
| `using-git-worktrees` | Isolated git worktrees |
| `finishing-a-development-branch` | Branch cleanup and merge prep |

## Multi-Agent Orchestration

| Skill | Trigger |
|-------|---------|
| `dispatching-parallel-agents` | 2+ independent tasks that can run concurrently |
| `subagent-driven-development` | Complex multi-file implementation |
| `executing-plans` | Following a written implementation plan |
| `maestro` | Multi-agent orchestration with task decomposition |

## Database

| Skill | Trigger |
|-------|---------|
| `database-migration` | Schema changes, migrations, database setup |

## Frontend & Design

| Skill | Trigger |
|-------|---------|
| `frontend-design` | Web components, pages, dashboards, landing pages |
| `ui-ux-pro-max` | UI/UX decisions, color, typography, layout |
| `webapp-testing` | Playwright browser testing |

## Documents & Formats

| Skill | Trigger |
|-------|---------|
| `docx` | Word documents (.docx) |
| `pdf` | PDF manipulation |
| `pptx` | PowerPoint (.pptx) |
| `xlsx` | Excel (.xlsx, .csv, .tsv) |

## Meta

| Skill | Trigger |
|-------|---------|
| `find-skills` | Discover/install new skills |
| `skill-creator` | Create or improve skills |
