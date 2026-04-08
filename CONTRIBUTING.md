# Contributing to Qryptum

Thank you for your interest in contributing to Qryptum.

## Getting started

1. Fork the repository you want to contribute to
2. Create a feature branch from `main`
3. Make your changes
4. Open a pull request with a clear description

## Code standards

- All code must pass TypeScript type checks
- Smart contract changes must include tests
- Maintain existing test coverage
- No console.log in production code
- All UI text must be in English

## Commit messages

Use conventional commit format:

```
feat: add new feature
fix: correct a bug
chore: update dependencies
docs: improve documentation
test: add or update tests
```

## Security issues

Do not open public issues for security vulnerabilities.
Please read our [Security Policy](SECURITY.md) and follow the responsible disclosure process.

## Pull request checklist

- [ ] Code compiles without errors
- [ ] Tests pass (contracts: `npm test`, app: `npm run typecheck`)
- [ ] No hardcoded secrets or private keys
- [ ] No em-dashes in any text, code, or comments
- [ ] Documentation updated if needed

## License

By contributing, you agree your contributions are licensed under the MIT License.
