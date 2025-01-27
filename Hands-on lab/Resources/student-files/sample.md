# Working with the Runbooks on VS COde

## Testing the Runbooks

If you cant to test the ASRRunBookWEB.ps1 or ASRRunBookSQL.ps1 with the Azure Automation VSCode Extension, you could use the following RecoveryPlanContext input

```json
{"RecoveryPlanName":"BCDRIaaSPlan","FailoverType":"Unplanned","FailoverDirection":"PrimaryToSecondary","GroupId":"FailoverAllActionGroup","VmMap":{}}
```
