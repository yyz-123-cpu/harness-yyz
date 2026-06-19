---
name: harness
description: Universal Harness management — init, status, update. Initialize projects with context templates, check harness state, update learnings.
---

# Harness Management Skill

This skill manages the single-agent Harness infrastructure for Claude Code. Use it to initialize new projects, check harness status, and update project context.

## Commands

### `/harness init`

Initialize a project with the Harness context structure.

**What it does:**
1. Creates `.claude/context/` with template files if they don't exist
2. Creates `.claude/memory/` directory if it doesn't exist
3. Drafts a project-level `CLAUDE.md` based on auto-detected tech stack
4. Seeds `.claude/context/project.md` with discovered project info

**Process:**
1. Auto-detect project type (Python/Node/Rust/Go/etc.) from files in CWD
2. Auto-detect tech stack (frameworks, build tools, package manager)
3. Fill in project.md, architecture.md, conventions.md, decisions.md from templates
4. Create project CLAUDE.md with brief tech-stack summary
5. Report what was created and what the user should fill in manually

**Template variables to fill:**
- `{{PROJECT_NAME}}` — project name from directory or package.json
- `{{PROJECT_TYPE}}` — detected type (python-web, node-cli, academic-paper, competition, etc.)
- `{{TECH_STACK}}` — detected stack (Python/Flask, Node/Express, etc.)
- `{{GOAL}}` — user should provide this; use placeholder if unknown

### `/harness status`

Show current harness state for the project.

**What it reports:**
- Project identity (name, type, tech stack)
- Context files present (.claude/context/*.md and their sizes)
- Memory entries count and last update time
- Git status summary
- Session history (approximate, from memory timestamps)

### `/harness update`

Update project context files based on recent work. Use after significant changes.

**What it does:**
1. Reviews recent changes (git diff, new files, deleted files)
2. Identifies what context files need updating
3. Proposes changes to user for approval
4. Applies approved changes
5. Saves new memory entries if applicable

## Templates

Template files are in `templates/`:
- `project.md` — Project overview: what, why, for whom
- `architecture.md` — System architecture: components, data flow, external dependencies
- `conventions.md` — Code conventions, naming patterns, commit style
- `decisions.md` — Key decisions log with rationale
- `environment.md` — Python/Node/Git paths, GPU info, known pitfalls

## References

- [Skill Routing Reference](references/skill-routing.md) — How skills are routed in the Harness ecosystem. Load on demand when skill selection is unclear.

## Integration

This skill is the entry point for the Harness ecosystem. Pair it with the global `CLAUDE.md` (the Harness operating protocol) for full Phase 0-4 auto-orient, context management, and skill dispatch.
