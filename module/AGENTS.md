# Lola Example Module

This module provides Go development standards for the team. Use these skills, commands, and agents to maintain consistent code quality across projects.

## When to Use

- **Review Checklist**: Use the `review-checklist` skill when reviewing any Go code change — PRs, diffs, or staged files.
- **Security Audit**: Use `/security-audit` to scan a project for hardcoded secrets, vulnerable dependencies, and insecure patterns.
- **Dependency Updater**: Delegate to `@dependency-updater` when upgrading Go modules or resolving dependency conflicts.

## Notes

- Always run tests after applying suggestions from any skill or agent.
- The security audit command is a quick scan, not a replacement for a full security review.
