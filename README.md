# Zimbra PowerShell Classes
PowerShell 5.x Class file for easily adding Zimbra user and resource management functionality to your own PowerShell scripts. This is not a cmdlet but a reusable set of Classes to incorporate in your own scripts.
I needed to write this Zimbra script to be part of the User provisioning scripts.
PowerShell 5.0 introduced ability to use real Classes, strongly typed properties and method returns.

This script uses Zimbra Admin Soap API, typically something like https://servername:7071/service/admin/soap/. Refer to https://wiki.zimbra.com/wiki/Zmsoap

# Using the script
Get current directory and include the file in your own script. You can either include the script with " . ZimbraManagementClasses.ps1" or below recommended way:

function Get-ScriptDirectory {<br />
    $Invocation = (Get-Variable MyInvocation -Scope 1).Value;<br />
    if($Invocation.PSScriptRoot) { $Invocation.PSScriptRoot}<br />
    Elseif($Invocation.MyCommand.Path) { Split-Path $Invocation.MyCommand.Path }<br />
    else { $Invocation.InvocationName.Substring(0,$Invocation.InvocationName.LastIndexOf("\")); }<br />
}<br />
$scriptPath = Get-ScriptDirectory;<br />
. $scriptPath"\ZimbraManagementClasses.ps1"<br />


