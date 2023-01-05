- アップグレードには2種類ある
	- Kubernetesのバージョンを更新せずにAKSクラスターのOSのバージョンを更新する
		- ホストクラスター
		- ワークロードクラスター
	- AKSクラスターのKubernetesバージョンを更新する
- AKSのホストクラスターの更新が常に最初の更新ステップとなる。ホストクラスター必ずUpdate-AksHciClusterコマンドを実施する前に実施する必要がある。

## 頻度
- 少なくとも60日に1回の更新が推奨されている。
- 30日ごとに新しいKubernetesバージョンの更新プログラムを利用可能となる。

## アップグレードプロセス
- サービスが中断しないようにローリングアップグレードが行われる。
- 


## 参考
- [PowerShell を使用して AKS ハイブリッドで Kubernetes バージョンのAzure Kubernetes Service (AKS) ワークロード クラスターをアップグレードする - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/upgrade)