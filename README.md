[![PowerShell](https://img.shields.io/badge/powershell--blue.svg?logo=powershell&longCache=true)](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/powershell)
[![Build Status](https://travis-ci.org/craigmayhew/windows.svg?branch=master)](https://travis-ci.org/craigmayhew/windows)

# Windows

So you have to use windows. Let's make it a bit less manual.

## Remove default apps

Open up powershell as admin:
```shell
Get-AppxPackage *3dbuilder* | Remove-AppxPackage
Get-AppxPackage *bingfinance* | Remove-AppxPackage
Get-AppxPackage *bingnews* | Remove-AppxPackage
Get-AppxPackage *bingsports* | Remove-AppxPackage
Get-AppxPackage *bingweather* | Remove-AppxPackage
Get-AppxPackage *getstarted* | Remove-AppxPackage
Get-AppxPackage *officehub* | Remove-AppxPackage
Get-AppxPackage *onenote* | Remove-AppxPackage
Get-AppxPackage *people* | Remove-AppxPackage
Get-AppxPackage *photos* | Remove-AppxPackage
Get-AppxPackage *skypeapp* | Remove-AppxPackage
Get-AppxPackage *solitairecollection* | Remove-AppxPackage
Get-AppxPackage *soundrecorder* | Remove-AppxPackage
Get-AppxPackage *windowsalarms* | Remove-AppxPackage
Get-AppxPackage *windowscalculator* | Remove-AppxPackage
Get-AppxPackage *windowscamera* | Remove-AppxPackage
Get-AppxPackage *windowscommunicationsapps* | Remove-AppxPackage
Get-AppxPackage *windowsmaps* | Remove-AppxPackage
Get-AppxPackage *windowsphone* | Remove-AppxPackage
Get-AppxPackage *xboxapp* | Remove-AppxPackage
Get-AppxPackage *zunemusic* | Remove-AppxPackage
Get-AppxPackage *zunevideo* | Remove-AppxPackage
```

## Chocolatey

Let's manage our software via the chocolatey repository.

Open a powershell as admin and install chocolatey:
```shell
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

Install software via packages!
```shell
choco install -y 7zip.install docker firefox notepadplusplus.install microsoft-windows-terminal slack vscode winmerge winscp wsl-ubuntu-1804 
```

## Theme
```shell
# set desktop background colour to black
Set-ItemProperty 'HKCU:\Control Panel\Colors' -Name Background -Value "0 0 0"
```

## Roadmap
 - [ ] Stop installing desktop shortcuts. Upstream functionality pending: https://github.com/chocolatey/choco/issues/4
 
## Blue Screen of Death
Ocassionally you may find yoursrlf in a blue screen of death scenario, use these tools to debug it!
 - BSOD viewer: https://www.nirsoft.net/utils/blue_screen_view.html
 - Find dump files here %systemroot%\Minidump
