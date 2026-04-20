# Contribution Context

Use this reference when the task is not just local coding but also contributor-facing WordPress Core work.

## Core Contribution Rules

- WordPress Core uses Trac as the official bug tracker.
- GitHub pull requests for Core should correspond to a Trac ticket.
- If preparing a PR for review, include the full Trac ticket URL in the PR body.

## Gutenberg Boundary

- WordPress Core and Gutenberg are related but not identical contribution surfaces.
- If the task is mainly Block Editor product work, Gutenberg is often the canonical repository.
- Use this skill when the ownership is clearly in WordPress Core or when you need to decide between Core and Gutenberg.

## Review Expectations

- Prefer minimal patches.
- Preserve backward compatibility unless explicitly changing a compatibility contract.
- Keep tests aligned with behavior.
- Update inline documentation when hooks, parameters, or public behavior change.

## Handbook Topics Worth Consulting

- Contributing with Code
- WordPress Coding Standards
- Inline Documentation Standards
- Browser Support Policies
- Spelling and grammar best practices