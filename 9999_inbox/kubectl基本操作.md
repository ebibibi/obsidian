## Windows環境へのPowerShellでのインストール

### Chocolateyでのインストール
```
rmdir -R C:\ProgramData\chocolatey\

Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

choco install kubernetes-cli
```

### 直接ダウンロード


(New-Object System.Net.WebClient).DownloadFile("https://storage.googleapis.com/kubernetes-release/release/v1.25.0/bin/windows/amd64/kubectl.exe","kubectl.exe")

### コンテキストの一覧を確認

kubectl config get-contexts

### 現在のコンテキストを確認

kubectl config current-context

### 全ての名前空間のコンテナイメージの一覧表示

kubectl get pods --all-namespaces

### Podのログの表示

kubectl logs <Pod名> -n 名前空間

### Pod内のコンテナを指定してログ表示

kubectl logs <Pod名> -c <コンテナ名> -n 名前空間

### ノードの状態の表示

kubectl describe nodes