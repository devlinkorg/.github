# Contribution Guidelines — Systems Reference

This document serves as the technical reference for contribution standards within DevLink. For the contributor-facing guide, see [CONTRIBUTING.md](../CONTRIBUTING.md).

---

## Code Standards

### General Principles

- Code must be self-documenting. Optimize for readability.
- Functions should be small and focused. Prefer composition over inheritance.
- Avoid premature optimization. Write correct code first, optimize with evidence.
- Handle errors explicitly. Do not silently swallow exceptions.

### Naming Conventions

| Element | Convention | Example |
|---|---|---|
| Files | kebab-case | `user-service.js` |
| Variables | camelCase | `userName` |
| Constants | UPPER_SNAKE_CASE | `MAX_RETRY_COUNT` |
| Classes | PascalCase | `UserService` |
| Functions | camelCase | `getUserById` |
| Database tables | snake_case | `user_sessions` |
| API endpoints | kebab-case | `/api/user-profile` |

### File Organization

- Group related files by feature, not by type.
- Keep file sizes manageable (generally under 300 lines).
- Use index files for module exports where appropriate.

---

## Documentation Standards

### Code Documentation

- All public interfaces must have documentation comments.
- Document the **why**, not the **what** — the code shows what it does.
- Include parameter descriptions and return types.

### Project Documentation

Every project must maintain:

| File | Purpose |
|---|---|
| `README.md` | Project overview, setup, and usage |
| `docs/` | Architecture decisions, API docs, guides |
| `CHANGELOG.md` | Version history and changes |

### Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>
```

- Use imperative mood.
- Keep the subject line under 72 characters.
- Provide context in the body when the change is non-trivial.

---

## Testing Standards

### Coverage Expectations

- New features: Must include unit tests covering primary paths and edge cases.
- Bug fixes: Must include a regression test.
- Refactoring: Existing tests must continue to pass without modification (unless the refactor intentionally changes behavior).

### Test Organization

- Tests live alongside source code or in a dedicated `tests/` directory (project-specific).
- Test files follow the naming convention: `{module}.test.{ext}` or `{module}.spec.{ext}`.
- Integration tests are separated from unit tests.

---

## Security Standards

- Never commit secrets, credentials, or API keys.
- Use environment variables for all configuration.
- Validate and sanitize all user input.
- Apply the principle of least privilege in all access controls.
- Report security vulnerabilities privately to the core team.

---

## Review Checklist

Reviewers should verify:

- [ ] Code compiles and passes all tests.
- [ ] Changes are covered by appropriate tests.
- [ ] Documentation is updated if behavior changes.
- [ ] No secrets or credentials are included.
- [ ] Code follows project naming and style conventions.
- [ ] Error handling is explicit and appropriate.
- [ ] No unnecessary dependencies are introduced.

---

## References

- [CONTRIBUTING.md](../CONTRIBUTING.md)
- [Architecture Standards](architecture.md)
- [Workflow Guide](workflow.md)
