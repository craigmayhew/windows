# Windows

So you have to use windows. Let's make it a bit less manual.
## Chocolatey

Let's manage our software via the chocolatey repository.

Open a powershell as admin and install chocolatey:
```shell
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

Install software via packages!
```shell
choco install -y slack vscode winmerge winscp
```

Set windows preferences!
```shell
# set desktop background colour to black
Set-ItemProperty 'HKCU:\Control Panel\Colors' -Name Background -Value "0 0 0"
```
