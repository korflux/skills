---
name: smartmemory-installation
description: 'Use when installing SmartMemory into a new or existing repository from the public GitHub source. Triggers: install SmartMemory, add SmartMemory to this repo, install persistent Copilot memory, set up SmartMemory in an existing project, SmartMemory GitHub template, SmartMemory INSTALL.md, SmartMemory .github and memory folders, /init prompt, scan project prompt, instalar SmartMemory, adicionar SmartMemory neste repositorio, adicionar memoria persistente do Copilot, configurar SmartMemory em projeto existente, template do SmartMemory no GitHub, pastas .github e memory do SmartMemory, prompt /init do SmartMemory, prompt scan project do SmartMemory. Do not use for generic GitHub Copilot setup, deep customization of SmartMemory internals, or local-path-only installation flows.'
argument-hint: 'Is this a new repository or an existing project, do .github or memory already exist, and do you want the GitHub template flow or an in-place install from SmartMemory?'
---

# SmartMemory Installation

Use this skill when installing SmartMemory into a repository from the public GitHub source.

This skill is for adding SmartMemory to new or in-progress repositories using the GitHub template, or by pulling only the `.github/` and `memory/` surfaces from the public SmartMemory repository. It focuses on safe install-mode selection, collision detection, non-destructive placement, and immediate post-install setup in Copilot Chat.

## What This Skill Produces

- A safe SmartMemory install path for the current repository state.
- GitHub-based install commands for Windows or POSIX shells.
- Clear collision handling for existing `.github/` and `memory/` content.
- A post-install checklist for placeholders, `/init`, `scan project`, and the first commit.

## When To Use

- Adding SmartMemory to a brand-new repository.
- Installing SmartMemory into an existing repository already checked out locally.
- Choosing between the GitHub template flow and an in-place install flow.
- Checking whether existing `.github/` or `memory/` content makes the install unsafe.
- Guiding the first Copilot steps after SmartMemory files land in the repository.

## Discovery Phrases

### English

- install SmartMemory in this repository
- add persistent Copilot memory to this project
- use the SmartMemory GitHub template
- install SmartMemory into an existing project
- pull SmartMemory .github and memory folders from GitHub
- set up SmartMemory placeholders and run /init
- add SmartMemory and then run scan project
- install SmartMemory without overwriting existing repo instructions

### Portuguese

- instale o SmartMemory neste repositorio
- adicione memoria persistente do Copilot a este projeto
- use o template do SmartMemory no GitHub
- instale o SmartMemory em um projeto existente
- traga as pastas .github e memory do SmartMemory pelo GitHub
- configure os placeholders do SmartMemory e rode /init
- adicione o SmartMemory e depois rode scan project
- instale o SmartMemory sem sobrescrever instrucoes existentes do repositorio

## Do Not Use

- Generic GitHub Copilot repository setup unrelated to SmartMemory.
- Deep changes inside SmartMemory's upstream repository.
- Local-path-only installation flows that other users cannot reproduce.
- Ongoing maintenance or merge strategy for an already customized SmartMemory install.

## Load These References As Needed

- For the default install flow, load [workflow](./references/smartmemory-installation-workflow.md).
- For choosing the correct install mode and handoff surface, load [routing](./references/smartmemory-installation-routing.md).
- For focused install checks, load [validation](./references/validation.md).
- For install ownership versus upstream or generic Copilot work, load [boundaries](./references/smartmemory-installation-boundaries.md).

## Procedure

1. Confirm the owner is SmartMemory installation for a repository.
   - If the goal is to add SmartMemory itself to a repository, continue here.
   - If the user wants generic Copilot standards or agents unrelated to SmartMemory, prefer a broader Copilot setup surface when one is available.
   - If the user is changing SmartMemory upstream internals, work in the SmartMemory repository itself rather than treating it as an install task.

2. Detect the target repository state first.
   - New repository with no code or config yet.
   - Existing repository with no `.github/` or `memory/`.
   - Existing repository with `.github/`, `memory/`, or both already present.

3. Choose the install mode from GitHub only.
   - Prefer the GitHub template flow for truly new repositories.
   - Prefer an in-place GitHub archive or copy-from-upstream flow for an existing checked-out repository.
   - Do not depend on a local `A:\OneDrive\@Pessoal\@ Skills` path.

4. Stop on collisions before writing.
   - If `.github/copilot-instructions.md` already exists, treat it as a collision.
   - If `memory/` already exists, treat it as a collision.
   - Ask before overwrite or merge. Do not guess.

5. Install the SmartMemory surfaces.
   - Land `.github/` and `memory/` at repository root.
   - Keep the upstream structure intact.
   - Use shell commands that match the user's platform when execution is requested.

6. Guide the immediate post-install flow.
   - Fill placeholders in `.github/copilot-instructions.md`.
   - For new or mostly empty repositories, recommend `/init`.
   - For existing codebases, recommend `scan project`.
   - Recommend committing `memory/` so the team shares the context.

7. Validate narrowly.
   - Confirm `.github/` and `memory/` are at repository root.
   - Confirm no local-path dependency remains in the instructions.
   - Confirm the chosen next prompt matches the repository state.

## Decision Points

### Template Or In-Place Install?

- GitHub template: for a truly new repository.
- In-place install: for an existing repository already checked out locally.

### Collision Or Clean Install?

- Clean install: no overlapping `.github/` or `memory/` content exists.
- Collision: any SmartMemory-owned file or directory already exists at the target paths.

### Which Follow-Up Prompt?

- `/init`: new repository or fresh install that still has placeholders to fill.
- `scan project`: existing codebase that needs `memory/modules.md` and `memory/registry.md` drafted from current code.
- `update memory`: later maintenance after work sessions, not the first install.