# Titles

This folder contains scripts, templates and other files used for the lab.

All files should be copied to the cloudworkshop storage account at <https://cloudworkshop.blob.core.windows.net/building-resilient-iaas-architecture/lab-resources/><VERSION>/

Use a different <VERSION> at each lab revision.

All links in the templates, scripts, student files, and also in the lab guides themselves will need to be updated when changing <VERSION>

Do not link directly to files in Github.

This approach makes it possible to work on lab updates in a separate branch without breaking existing labs.

Notes

## Code

```PowerShell
Get-Module -Name Az* -ListAvailable

uninstall specific modules
Uninstall-Module -Name Az.Resources -AllVersions

find latest version of a modules
Find-Module -Name Az.Accounts

install module with specific version
Install-Module -Name Az.Accounts -RequiredVersion 2.12.1
```

Connect-AzAccount
<https://learn.microsoft.com/en-us/powershell/module/az.accounts/connect-azaccount>

Migrate from an existing Run As account to Managed identities
<https://learn.microsoft.com/en-us/azure/automation/migrate-run-as-accounts-managed-identity>

Using a system-assigned managed identity for an Azure Automation account
<https://learn.microsoft.com/en-us/azure/automation/enable-managed-identity-for-automation>

Use Azure Automation extension for Visual Studio Code
<https://learn.microsoft.com/en-us/azure/automation/how-to/runbook-authoring-extension-for-vscode>
