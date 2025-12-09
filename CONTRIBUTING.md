# Contributing to CodeFlow Azure Setup

Thank you for your interest in contributing to CodeFlow Azure Setup scripts! This document provides guidelines for PowerShell script contributions.

---

## Getting Started

1. **Fork the repository** on GitHub
2. **Clone your fork** locally
3. **Set up development environment**:
   - PowerShell 7+
   - Azure CLI installed and configured
   - PSScriptAnalyzer (for linting)
4. **Create a branch** for your changes

---

## Development Workflow

### Prerequisites

- PowerShell 7+
- Azure CLI
- PSScriptAnalyzer: `Install-Module -Name PSScriptAnalyzer -Scope CurrentUser`

### Code Style

- Follow PSScriptAnalyzer rules
- Use approved verbs for function names
- Add comprehensive help comments
- Use proper error handling with try-catch
- Use `$ErrorActionPreference = 'Stop'` for scripts

**Before committing:**
```powershell
# Lint scripts
Invoke-ScriptAnalyzer -Path .\scripts\*.ps1

# Validate syntax
Get-ChildItem -Recurse -Filter "*.ps1" | ForEach-Object {
    $null = [System.Management.Automation.PSParser]::Tokenize(
        (Get-Content $_.FullName -Raw), [ref]$null
    )
}
```

---

## Pull Request Process

1. **Validate scripts** with PSScriptAnalyzer
2. **Test scripts** in a development environment
3. **Update documentation** as needed
4. **Create a pull request** with a clear description

### PR Checklist

- [ ] Scripts pass PSScriptAnalyzer
- [ ] Scripts tested in development environment
- [ ] Error handling implemented
- [ ] Documentation updated
- [ ] No hardcoded credentials

---

## Commit Message Format

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
fix(setup): resolve Azure login issue

Add retry logic for Azure CLI login.
Improve error messages for authentication failures.

Fixes #123
```

---

## Reporting Issues

Use GitHub Issues with:
- Clear description
- Affected script
- Steps to reproduce
- Error messages
- PowerShell version
- Azure CLI version

---

## Questions?

- GitHub Discussions: For questions
- GitHub Issues: For bugs and features
- See [main CONTRIBUTING guide](../../codeflow-orchestration/docs/CONTRIBUTING_TEMPLATE.md) for more details

---

Thank you for contributing! 🎉

