# CodeFlow Azure Setup Scripts

Generic, org-agnostic PowerShell scripts to bootstrap Azure environments for new repositories using the `org-env-project-type-region` naming convention.

## Purpose

This repository contains reusable Azure infrastructure bootstrapping scripts that can be used for **any** repository or project. These scripts are:

- **Generic**: No app-specific assumptions
- **Reusable**: Work for any project with the naming convention
- **Org-agnostic**: Use parameters (OrgCode, Environment, Project) rather than hard-coded values

## Quick Start

See the [scripts documentation](scripts/README-AZURE-SETUP.md) for detailed usage instructions.

### Example

```powershell
.\scripts\New-AzRepoEnvironment.ps1 `
  -OrgCode nl `
  -Environment dev `
  -Project myproject `
  -RegionShort san `
  -Location southafricanorth `
  -SubscriptionId <your-subscription-id> `
  -CreateKeyVault `
  -OutputJsonPath ./az-env-dev-myproject.json
```

## Scripts

1. **`New-AzRepoEnvironment.ps1`** - Creates core Azure infrastructure (resource group, storage, Log Analytics, App Insights, optional Key Vault)
2. **`New-AzRepoFullEnvironment.ps1`** - Creates full environment including App Service, Web App, Container Apps, and managed identity
3. **`Set-GitHubSecretsFromJson.ps1`** - Creates GitHub repository secrets from JSON output

## Requirements

- PowerShell 7+
- Azure CLI (`az`) - logged in and targeting correct subscription
- GitHub CLI (`gh`) - for secrets helper script

## Repository Structure

```
codeflow-azure-setup/
├── scripts/
│   ├── New-AzRepoEnvironment.ps1
│   ├── New-AzRepoFullEnvironment.ps1
│   ├── Set-GitHubSecretsFromJson.ps1
│   └── README-AZURE-SETUP.md
└── README.md (this file)
```

## Important Boundary Rule

**This repository contains ONLY generic bootstrap scripts.**

- ✅ Generic, reusable scripts
- ✅ Org-agnostic naming (OrgCode, Environment, Project parameters)
- ❌ CodeFlow-specific infrastructure
- ❌ Production CA environments, VNets, DNS
- ❌ Anything that would require maintaining IaC in two places

For CodeFlow-specific or production-grade infrastructure, see [`codeflow-infrastructure`](https://github.com/JustAGhosT/codeflow-infrastructure).

## License

MIT

