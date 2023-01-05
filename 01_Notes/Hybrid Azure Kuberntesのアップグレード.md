- アップグレードには2種類ある
	- Kubernetesのバージョンを更新せずにAKSハイブリッドホストを更新する
	- Kubernetesバージョンを更新する
- AKSハイブリッドホストの更新が常に最初の更新ステップとなる。最後がKubernetesバージョンの更新となる。

## 頻度
- AKSハイブリッドホスト
	- 新しいAKSホストの更新から30日以内にAKSクラスターをアップグレードすることが推奨されている。
	- <mark style="background: #FF5582A6;">最後のアップグレードから90日以内にアップグレードを行わないと内部証明書とトークンの有効期限が切れてしまい、アップグレードのためにMicrosoftサポートの協力を得る必要が出てしまう。</mark>
- Kubernetes
	- 少なくとも60日に1回の更新が推奨されている。
	- 30日ごとに新しいKubernetesバージョンの更新プログラムが利用可能となる。

## アップグレードプロセス
- サービスが中断しないようにローリングアップグレードが行われる。

## PowerShellでのアップグレードプロセス実行例
```
#############################
# AKSハイブリッドホストの更新 #
#############################

# PowerShellモジュールを最新にする(全ノードでの実行)
Update-Module -Name AksHci -Force -AcceptLicense

# 現在のAKSハイブリッドバージョンを取得
Get-AksHciVersion

# 利用可能なAKSハイブリッド更新プログラムの取得
Get-AksHciUpdates

#管理クラスターを最新バージョンに更新
Update-AksHci

# AKSホストが更新されたことを確認する
Get-AksHciVersion

###################
# Kubernetesの更新 #
###################

# 利用可能なKubernetesバージョンの取得
Get-AksHciKubernetesVersion

# 利用可能なKubernetesバージョンの取得
Get-AksHciClusterUpdates -name myCluster

# Kubernetesのバージョン更新
Update-AksHciCluster -name myCluster -kubernetesVersion vX.XX.X

```



## 参考
- [概念 - PowerShell を使用して AKS ハイブリッドの AKS ホストをアップグレードする - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/update-akshci-host-powershell)
- [PowerShell を使用して AKS ハイブリッドで Kubernetes バージョンのAzure Kubernetes Service (AKS) ワークロード クラスターをアップグレードする - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/upgrade)