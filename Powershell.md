# Powershell Resources
* Azure Powershell: https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-4.3.1
    * Azure AD Powershell: https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0
* Cookbooks: https://docs.microsoft.com/en-us/powershell/scripting/getting-started/cookbooks/creating-.net-and-com-objects--new-object-?view=powershell-5.1
* Channel 9:
   * Basics: https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1
   * https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShell-Basics-Part-2-Real-Word-Examples-for-Our-Most-Common-Cmdlets
* Powershell's Intellisense: https://blogs.msdn.microsoft.com/powershell/2012/06/12/intellisense-in-windows-powershell-ise-3-0/


# Notes
## from Channel 9 Basic video:
*  Get-PSDrive
   * Lists all providers
*  cmd /c set
   * runs a dos command when there is no PS alias
*  Get-PSDrive | foreach-Object {$PSDrive=$_.Name; "`nPSDrive: `t$PSDrive"; Get-ChildItem "$($_.Name):" | Select-Object -First 1}
   * iterates each provider and displays first child item of each
*  Add-Type -AssemblyName System.Windows.Forms
   * adds assembly reference
*  Add-AzureAccount or Add-RmAzzureAccount
   * prompts for Azure credentials
*  Select-AzureRmSubscription -SubscriptionId a0a6519a-e86d-4327-8cf9-55fdb6b17541
   * downloads subscription information into appdata\roaming making it available for powersheel azure cmdlets
*  Get-AzureRmSqlDatabase -ResourceGroupName "m7computers" -ServerName "m7sql" -DatabaseName m7computers
   * get azure databases in resource group m7computers


*  get-help *-service

*  get-service -name sql*

*  get-alias | where-object {$_.ResolvedCommandName -eq "Remove-Item"}

*  get-command -name get*

*  $env:PSModulePath.Split(";")

*  Get-Module -ListAvailable

*  Get-Module azure | Measure-Object

*  get-command -Module Microsoft.Powershell.utility | measure-object

*  get-verb | sort-object -property verb

*  Get-command -Noun variable

*  get-help Get-Variable

*  Get-Variable -Name PSVersionTable -Valueonly

*  Get-AzureSqlDatabaseServer | Where-object{$_.ServerName -match "7"}
   * find Sql Servers with a 7 in the name

### Get-Item . 
* list default properties of the current folder.  there are only 3
### Get-Item . | Select-Object -Proeprty *
* list all properties of the current folder

### Get-Module Azure | Select-Object -Property Path
* lists folder and path of PS Module "azure"

### Get-Module Azure | Select-Object -ExpandProperty Path
* returns just the value of the Path proeprty, omits the label "Path" and other formatting from the output

### (ping $env:COMPUTERNAME -4 | Select-Object -skip 2 -First 1).Split()
*  return computer name extracted from 3rd line of output from ping command
* could also use:  (ping localhost -4 | Select-Object -skip 2 -First 1).Split()

### ((ping localhost -4 | Select-Object -skip 2 -First 1).Split() | Where-object {$_ -like "*.*.*.*"}).trim().trimend(":")
* extracts the IPv4 address form the Ping

### Install-Module AzureAD
*  installs General Available Azure AD 2.0
* see https://docs.microsoft.com/en-us/powershell/azure/active-directory/install-adv2?view=azureadps-2.0







