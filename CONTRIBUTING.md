# Contributing to OperationsPAI

Thank you for your interest in contributing to OperationsPAI! This guide will help you get started.

## Getting Started

### Prerequisites

Before contributing, please:

1. Read our [Code of Conduct](CODE_OF_CONDUCT.md)
2. Review the [project vision](docs/community/vision.md)
3. Check the [roadmap](ROADMAP.md) to understand current priorities

### First-Time Contributors

If you're new to the project, start with:

1. **Verify Documentation**: Run through our Quick Start guide and report issues
2. **Good First Issues**: Look for issues labeled `good-first-issue`
3. **Ask Questions**: Don't hesitate to ask in GitHub Discussions

## How to Contribute

### 1. Code Contributions

**Finding Work:**
- Browse [open issues](https://github.com/OperationsPAI) across our repositories
- Check the [roadmap](ROADMAP.md) for planned features
- Propose new ideas in GitHub Discussions

**Development Workflow:**

```bash
# 1. Fork the repository
# 2. Clone your fork
git clone https://github.com/YOUR_USERNAME/REPO_NAME.git

# 3. Create a feature branch
git checkout -b feature/your-feature-name

# 4. Make your changes
# Follow the coding standards in each repository's CLAUDE.md

# 5. Run tests
# See repository-specific testing instructions

# 6. Commit with clear messages
git commit -m "feat: add new feature description"

# 7. Push to your fork
git push origin feature/your-feature-name

# 8. Open a Pull Request
```

**Commit Message Format:**

```
<type>: <description>

[optional body]
```

Types: `feat`, `fix`, `docs`, `test`, `refactor`, `chore`

### 2. Documentation Contributions

Documentation is crucial for community growth:

- **Fix Errors**: Correct typos, broken links, or outdated information
- **Add Examples**: Provide real-world usage examples
- **Translate**: Help translate documentation to other languages
- **Improve Clarity**: Simplify complex explanations

### 3. Testing and Bug Reports

Help us improve quality:

- **Verify Installation**: Test on different platforms (Linux, macOS, Windows)
- **Report Bugs**: Use our [bug report template](.github/ISSUE_TEMPLATE/bug_report.md)
- **Write Tests**: Add unit, integration, or E2E tests

### 4. Community Support

Support other community members:

- **Answer Questions**: Help others in GitHub Discussions
- **Review Pull Requests**: Provide constructive feedback
- **Share Knowledge**: Write blog posts or tutorials

## Pull Request Guidelines

### Before Submitting

- [ ] Code follows repository coding standards
- [ ] Tests pass locally
- [ ] Documentation is updated
- [ ] Commit messages are clear
- [ ] PR description explains the change

### PR Description Template

```markdown
## Description
Brief description of what this PR does

## Motivation
Why is this change needed?

## Changes
- List of specific changes

## Testing
How was this tested?

## Screenshots (if applicable)
Add screenshots for UI changes
```

### Review Process

1. **Automated Checks**: CI/CD runs tests and linters
2. **Code Review**: Maintainers review your code
3. **Feedback**: Address review comments
4. **Approval**: Once approved, maintainers will merge

## Contributor Ladder

We recognize contributions at different levels:

### 1. Contributor
- Made at least one merged contribution
- Listed in repository contributors

### 2. Active Contributor
- 5+ merged contributions
- Regular participation in discussions
- Invited to contributor meetings

### 3. Reviewer
- 20+ merged contributions
- Deep knowledge of specific components
- Can review and approve PRs

### 4. Maintainer
- Sustained contributions over 6+ months
- Trusted with repository write access
- Participates in governance decisions

### 5. Core Team
- Strategic leadership
- Cross-repository expertise
- Represents the project publicly

## Development Resources

### Repository Structure

- **AegisLab**: Core orchestration platform
- **chaos-experiment**: Fault injection framework
- **train-ticket**: Demo microservices application
- **loadgenerator**: Traffic generation tool
- **Pandora**: Intelligent fault scheduler
- **rcabench-platform**: Algorithm evaluation framework

### Key Technologies

- **Languages**: Go, Python, Java
- **Infrastructure**: Kubernetes, Docker, Helm
- **Observability**: OpenTelemetry, Prometheus, ClickHouse
- **Chaos Engineering**: Chaos Mesh

### Learning Resources

- [Architecture Overview](docs/community/resources.md)
- [Quick Start Guide](https://operationspai.github.io/quickstart)
- [Video Tutorials](https://operationspai.github.io/tutorials)

## Getting Help

- **GitHub Discussions**: [Ask questions](https://github.com/OperationsPAI/operationspai.github.io/discussions)
- **GitHub Issues**: [Report bugs](https://github.com/OperationsPAI)
- **Email**: (to be established for sensitive matters)

## Recognition

We value all contributions:

- Contributors are listed in repository READMEs
- Significant contributions are highlighted in release notes
- Active contributors are invited to co-author research papers
- Community achievements are celebrated on social media

## License

By contributing, you agree that your contributions will be licensed under the same license as the project (typically Apache 2.0 or MIT - check individual repositories).

---

**Thank you for contributing to OperationsPAI!** Your efforts help build a better RCA ecosystem for everyone.
