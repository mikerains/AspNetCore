# Powershell Resources
* Azure Powershell: https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-4.3.1
* Cookbooks: https://docs.microsoft.com/en-us/powershell/scripting/getting-started/cookbooks/creating-.net-and-com-objects--new-object-?view=powershell-5.1
* Channel 9:
  * Basics: https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1
  * 
* Powershell's Intellisense: https://blogs.msdn.microsoft.com/powershell/2012/06/12/intellisense-in-windows-powershell-ise-3-0/


# Notes
## from Channel 9 Basic video:
### Get-PSDrive
Lists all providers
### cmd /c set
runs a dos command when there is no PS alias
### Get-PSDrive | foreach-Object {$PSDrive=$_.Name; "`nPSDrive: `t$PSDrive"; Get-ChildItem "$($_.Name):" | Select-Object -First 1}
iterates each provider and displays first child item of each
### Add-Type -AssemblyName System.Windows.Forms
adds assembly reference
### Add-Account
prompts for Azure credentials
### Select-AzureRmSubscription -SubscriptionId a0a6519a-e86d-4327-8cf9-55fdb6b17541
downloads subscription information into appdata\roaming making it available for powersheel azure cmdlets
### Get-AzureRmSqlDatabase -ResourceGroupName "m7computers" -ServerName "m7sql" -DatabaseName m7computers
get azure databases in resource group m7computers


## get-help *-service

### get-service -name sql*

### get-alias | where-object {$_.ResolvedCommandName -eq "Remove-Item"}

### get-command -name get*

### $env:PSModulePath.Split(";")

### Get-Module -ListAvailable

### Get-Module azure | Measure-Object

### get-command -Module Microsoft.Powershell.utility | measure-object

### get-verb | sort-object -property verb

### Get-command -Noun variable

### get-help Get-Variable

### Get-Variable -Name PSVersionTable -Valueonly


