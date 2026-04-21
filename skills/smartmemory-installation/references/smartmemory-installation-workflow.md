# SmartMemory Installation Workflow

Use this reference when installing SmartMemory into a new or existing repository.

## Default Flow

1. Start from repository state.
   - Decide whether the target is a truly new repository or an existing checked-out project.
   - Detect whether `.github/copilot-instructions.md`, `memory/`, or both already exist.
   - Treat an existing `.github/` directory by itself as non-blocking when the SmartMemory-owned files are still absent.

2. Choose the GitHub-only install mode.
   - New repository: prefer the GitHub template flow.
   - Existing repository: prefer an in-place install using the public SmartMemory repository artifacts.
   - Do not rely on a local path that other users cannot reproduce.

3. Treat collisions as a decision point.
   - If `.github/copilot-instructions.md` exists, stop and treat it as a collision.
   - If `memory/` exists, stop and treat it as a collision.
   - Do not overwrite or merge silently.

4. Place the SmartMemory surfaces at repository root.
   - Install `.github/`.
   - Install `memory/`.
   - Preserve the upstream folder structure exactly.

## Execution Patterns

### New Repository: GitHub Template

1. Open `https://github.com/korflux/SmartMemory`.
2. Click `Use this template`.
3. Create the new repository from that template.
4. Clone the new repository and start the post-install flow.

### Existing Repository: In-Place Install On Linux Or macOS

Run from the target repository root:

```bash
curl -L https://github.com/korflux/SmartMemory/archive/refs/heads/main.tar.gz \
   | tar -xz --strip-components=1 SmartMemory-main/.github SmartMemory-main/memory
```

### Existing Repository: In-Place Install On Windows PowerShell

Run from the target repository root:

```powershell
$tmp = Join-Path $env:TEMP "smartmemory.zip"
Invoke-WebRequest -Uri "https://github.com/korflux/SmartMemory/archive/refs/heads/main.zip" -OutFile $tmp
Expand-Archive -Path $tmp -DestinationPath $env:TEMP\smartmemory-extract -Force
Copy-Item -Recurse "$env:TEMP\smartmemory-extract\SmartMemory-main\.github" .github
Copy-Item -Recurse "$env:TEMP\smartmemory-extract\SmartMemory-main\memory" memory
Remove-Item $tmp, "$env:TEMP\smartmemory-extract" -Recurse -Force
```

### Immediate Post-Install Prompts

- New or mostly empty repository: run `/init` in Copilot Chat.
- Existing codebase: run `scan project` in Copilot Chat.
- Later maintenance: run `update memory` or `atualizar memoria`.

5. Run the immediate post-install flow.
   - Fill placeholders in `.github/copilot-instructions.md`.
   - Recommend `/init` for a new or mostly empty repository.
   - Recommend `scan project` for an existing codebase.

6. Finish with repository hygiene.
   - Confirm the install came from `https://github.com/korflux/SmartMemory`.
   - Recommend committing the `memory/` folder so the whole team shares the context.

## Red Flags

- Using a local source path instead of the public GitHub repository.
- Copying only part of `.github/` or only part of `memory/`.
- Overwriting existing repository instructions without confirmation.
- Recommending `/init` for a mature codebase that really needs `scan project`.
- Treating SmartMemory installation as generic Copilot bootstrap work.