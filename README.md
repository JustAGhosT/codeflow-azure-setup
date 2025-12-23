# ⚠️ DEPRECATED - Repository Archived

> **This repository has been merged into [codeflow-orchestration](https://github.com/JustAGhosT/codeflow-orchestration).**

---

## New Location

All Azure bootstrap scripts have been moved to the `codeflow-orchestration` repository:

| Component | Old Location | New Location |
|-----------|--------------|--------------|
| PowerShell Scripts | `scripts/` | `codeflow-orchestration/bootstrap/scripts/` |
| Documentation | `scripts/README-AZURE-SETUP.md` | `codeflow-orchestration/bootstrap/README.md` |
| CI/CD Workflows | `.github/workflows/` | `codeflow-orchestration/bootstrap/.github/workflows/` |

---

## Migration Guide

### Clone the New Repository

```bash
git clone https://github.com/JustAGhosT/codeflow-orchestration.git
cd codeflow-orchestration/bootstrap/scripts
```

### Update Your Script References

If you have scripts or workflows referencing this repository, update them:

```powershell
# Old
./codeflow-azure-setup/scripts/New-AzRepoEnvironment.ps1

# New
./codeflow-orchestration/bootstrap/scripts/New-AzRepoEnvironment.ps1
```

### Update Your Bookmarks

- **Old:** `https://github.com/JustAGhosT/codeflow-azure-setup`
- **New:** `https://github.com/JustAGhosT/codeflow-orchestration/tree/main/bootstrap`

---

## Available Scripts (New Location)

All scripts are now at `codeflow-orchestration/bootstrap/scripts/`:

| Script | Purpose |
|--------|---------|
| `New-AzRepoEnvironment.ps1` | Create core Azure resources (RG, Storage, Log Analytics, App Insights) |
| `New-AzRepoFullEnvironment.ps1` | Full environment with App Service, Container Apps, Managed Identity |
| `Set-GitHubSecretsFromJson.ps1` | Configure GitHub secrets from Azure output |

---

## Why This Change?

1. **Single source of truth** - All infrastructure and orchestration in one place
2. **Clear separation** - Bootstrap (generic) vs Infrastructure (CodeFlow-specific)
3. **Simplified maintenance** - One repository to manage
4. **Reduced repository sprawl** - 7 repos → 5 repos

---

## Questions?

If you have questions about this migration, please:
1. Open an issue in [codeflow-orchestration](https://github.com/JustAGhosT/codeflow-orchestration/issues)
2. Review the [Infrastructure Consolidation Plan](https://github.com/JustAGhosT/codeflow-orchestration/blob/main/docs/INFRASTRUCTURE_CONSOLIDATION_PLAN.md)

---

**Archived:** 2025-01-XX
**Migration completed by:** Infrastructure Team
