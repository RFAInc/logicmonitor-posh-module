# General
Windows PowerShell module for accessing the LogicMonitor REST API.

This project is also published in the PowerShell Gallery at https://www.powershellgallery.com/packages/LogicMonitor/.

# Installation
* From PowerShell Gallery: Install-Module -Name LogicMonitor
* From GitHub: Save `/bin/<version>/LogicMonitor/<files>` to your module directory

# Behavior changes
## 1.0.1.17
* When Invoke-Request returns an error, all cmdlets return more data about the contents. Previously, the exception message was all that was returned.
* Added check for 429 respone to all cmdlets, to detect a rate-limiting situation and retry the request. Previously, only some of the cmdlets detected rate limiting.
## 1.0.1.12
* The cmdlets now require AccessKey to be a secure string.
## 1.0.1.10
* Add-LogicMonitorDeviceGroup no longer accepts properties as two separate parameters. Instead, the cmdlet requires a hash table of desired properties. Name and ParentId remain required.
* Add-LogicMonitorDevice no longer accepts properties as two separate parameters. Instead, the cmdlet requires a hash table of desired properties. Removed the HostGroupId requirement.