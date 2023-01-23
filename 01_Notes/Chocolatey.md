Windows用のパッケージマネージャー。wingetよりもずっと歴史が古い。

## インストール
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

## パッケージインストール
```
choco install <packagename> -y
```
