# autopilot-scripts
Autopilot-scripts - for VM's
 Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass -Force                               PS C:\Windows\system32> # Autopilot Information Collection Script                                                       PS C:\Windows\system32> # ----------------------------------------
PS C:\Windows\system32> # 1. Allow running this script temporarily
PS C:\Windows\system32> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass -Force
PS C:\Windows\system32>
PS C:\Windows\system32> # 2. Install Get-WindowsAutoPilotInfo if not already installed
PS C:\Windows\system32> if (-not (Get-Command Get-WindowsAutoPilotInfo -ErrorAction SilentlyContinue)) {
>>     Write-Host "Installing Get-WindowsAutoPilotInfo..."
>>     Install-Script -Name Get-WindowsAutoPilotInfo -Force
>> }
Installing Get-WindowsAutoPilotInfo...

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The NuGet
 provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\DELL\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider by running
'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import
 the NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
PS C:\Windows\system32>
PS C:\Windows\system32> # 3. Run Get-WindowsAutoPilotInfo and save output to C:\Computer.csv
PS C:\Windows\system32> Write-Host "Collecting device info and exporting to C:\Computer.csv..."
Collecting device info and exporting to C:\Computer.csv...
PS C:\Windows\system32> Get-WindowsAutoPilotInfo.ps1 -OutputFile C:\Computer.csv
Gathered details for device with serial number: H9N23F3
PS C:\Windows\system32>
PS C:\Windows\system32> Write-Host "Done! File saved to C:\Computer.csv"
Done! File saved to C:\Computer.csv
PS C:\Windows\system32>
