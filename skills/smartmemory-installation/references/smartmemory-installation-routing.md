# SmartMemory Installation Routing

Use this reference when choosing the correct SmartMemory installation path for the target repository.

## Route To GitHub Template When

- The target repository does not exist yet, or the user is still creating it.
- The user wants SmartMemory present from the first commit.
- There is no local project state that must be preserved during installation.

## Route To In-Place Install When

- The repository already exists locally.
- The user needs to add SmartMemory without recreating the repository.
- The repository can accept `.github/` and `memory/` at root after collision checks pass.

## Stop And Ask Before Continuing When

- `.github/copilot-instructions.md` already exists.
- `memory/` already exists.
- Another Copilot instruction layout is already present and ownership is unclear.

## Route Away From This Skill When

- The task is generic GitHub Copilot repository setup unrelated to SmartMemory.
- The task is about changing SmartMemory upstream files or release mechanics.
- The task is about maintaining or merging an already customized SmartMemory install rather than performing the first installation.

If a broader Copilot setup surface exists for the repository, route there instead of forcing SmartMemory installation to own generic Copilot work.