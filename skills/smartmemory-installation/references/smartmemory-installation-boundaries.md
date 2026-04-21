# SmartMemory Installation Boundaries

Use this reference when deciding whether a task belongs in SmartMemory installation, SmartMemory upstream work, or generic Copilot setup.

## SmartMemory Installation Owns

- Adding SmartMemory to a new or existing repository from the public GitHub source.
- Choosing between GitHub template and in-place installation.
- Collision-safe placement of `.github/` and `memory/`.
- Immediate post-install guidance such as placeholders, `/init`, and `scan project`.

## Route To SmartMemory Upstream Work When

- The change belongs inside the SmartMemory repository itself.
- The task changes the shipped `.github/` instructions, prompts, or `memory/` model as a product change.
- The task is about SmartMemory release content rather than consumer installation.

## Route To Generic Copilot Setup When

- The task is generic repository-wide Copilot configuration with no SmartMemory requirement.
- The user wants broader Copilot agents, workflows, or conventions that are independent of SmartMemory.

## Out Of Scope For This First Skill

- Automatic merge logic for conflicting `.github/` or `memory/` content.
- Ongoing maintenance of a previously customized SmartMemory install.
- Local-path-only install flows that third parties cannot reproduce.