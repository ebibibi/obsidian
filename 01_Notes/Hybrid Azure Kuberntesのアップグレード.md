- アップグレードには2種類ある
	- Kubernetesのバージョンを更新せずにAKSクラスターのOSのバージョンを更新する
		- ホストクラスター
		- ワークロードクラスター
	- AKSクラスターのKubernetesバージョンを更新する
- AKSのホストクラスターの更新が常に最初の更新ステップとなる。ホストクラスターを更新後にワークロードクラスターを更新し、最後がKubernetesバージョンの更新となる。

## 頻度
- 新しいAKSホストの更新から30日以内にAKSクラスターをアップグレードすることが推奨されている。
	- <mark style="background: #FF5582A6;">最後のアップグレードから90日以内にアップグレードを行わないと内部証明書とトークンの有効期限が切れてしまい、アップグレードのためにMicrosoftサポートの協力を得る必要が出てしまう。</mark>
- 少なくとも60日に1回の更新が推奨されている。
- 30日ごとに新しいKubernetesバージョンの更新プログラムを利用可能となる。

## アップグレードプロセス
- サービスが中断しないようにローリングアップグレードが行われる。

## コマンド
```
# PowerShellm
Update-Module -Name AksHci -Force -AcceptLicense
Update-AksHci #管理クラスターを最新バージョンに更新

```


## 参考
- [概念 - PowerShell を使用して AKS ハイブリッドの AKS ホストをアップグレードする - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/update-akshci-host-powershell)
- [PowerShell を使用して AKS ハイブリッドで Kubernetes バージョンのAzure Kubernetes Service (AKS) ワークロード クラスターをアップグレードする - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/upgrade)