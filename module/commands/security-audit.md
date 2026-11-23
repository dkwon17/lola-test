---
description: Scan the current project for hardcoded secrets, vulnerable dependencies, and insecure patterns.
argument-hint: "[path]"
---

Scan the project for common security issues. If `$ARGUMENTS` names a path, limit the scan to that subtree; otherwise scan the entire working directory.

## Workflow

1. Search for hardcoded secrets: API keys, tokens, passwords, and private keys in source files. Check `.env` files, config files, and string literals. Exclude test fixtures that use obviously fake values.
2. Check Go dependencies for known vulnerabilities by running `govulncheck ./...` if available, or by inspecting `go.sum` for packages with known CVEs.
3. Look for insecure patterns: disabled TLS verification, use of `md5` or `sha1` for security purposes, SQL string concatenation, and command injection via `os/exec` with unsanitized input.
4. Check file permissions on scripts and config files for overly permissive modes (world-writable).

## Output

Report findings grouped by severity (critical, warning, info). For each finding, include the file path, line number, and a one-line description of the issue with a suggested fix.
