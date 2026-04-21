# SmartMemory Installation Validation

Use this reference when validating a SmartMemory installation plan or execution.

## Minimum Checks

1. Validate file placement.
   - `.github/` should exist at repository root.
   - `memory/` should exist at repository root.
   - SmartMemory-specific files should not be nested under an extra wrapper folder.

2. Validate source assumptions.
   - The install path should reference `https://github.com/korflux/SmartMemory`.
   - No step should depend on `A:\OneDrive\@Pessoal\@ Skills` or any other local-only path.
   - The documented PowerShell and POSIX install commands should stay aligned with upstream `INSTALL.md` semantics.

3. Validate collision handling.
   - Existing `.github/copilot-instructions.md` should trigger a stop-and-confirm path.
   - Existing `memory/` should trigger a stop-and-confirm path.
   - No silent overwrite should be recommended.

4. Validate post-install guidance.
   - New or mostly empty repositories should be guided toward `/init`.
   - Existing codebases should be guided toward `scan project`.
   - Placeholder handling in `.github/copilot-instructions.md` should be called out explicitly.

5. Validate repository hygiene.
   - The install plan should recommend committing `memory/`.
   - The install plan should not imply that SmartMemory maintenance is complete after file copy alone.

## Escalate Only If Needed

- Add broader repository checks only when the task also changes existing Copilot instructions, workflows, or repository automation.