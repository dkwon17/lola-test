---
name: review-checklist
description: "Review checklist for a Go change: tests, error handling, concurrency, and rollback."
---

# Review Checklist

When reviewing Go code changes, verify each item below and report findings grouped by category.

## Error Handling

- Every returned error is checked or explicitly discarded with a comment.
- Errors wrap context with `fmt.Errorf("doing X: %w", err)` rather than bare returns.
- No panics in library code; panics in main are acceptable only for unrecoverable startup failures.

## Tests

- New exported functions have at least one test case covering the happy path.
- Table-driven tests use `t.Run` with descriptive subtest names.
- Tests do not depend on external services or network access unless marked with a build tag.

## Concurrency

- Shared state accessed from multiple goroutines is protected by a mutex or channel.
- Context cancellation is propagated, not swallowed.
- Goroutines started in a function have a clear shutdown path (context, done channel, or WaitGroup).

## API and Compatibility

- Exported function signatures match the existing style in the package.
- Breaking changes to public APIs are called out explicitly in the review summary.
- Deprecated functions include a `// Deprecated:` comment naming the replacement.

## Rollback Safety

- Database migrations have a corresponding rollback migration.
- Feature flags gate new behavior that could be reverted without a deploy.
- Configuration changes are backward-compatible with the previous release.
