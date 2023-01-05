Hybrid Azure Kubernetes Service。

## AKSを動かせる場所が広がる話
- AKS on Azure Stack HCIはHybrid Azure Kubernetes Service
	- 2020/9/22にパブリックプレビュー
		- [Azure Kubernetes Service on Azure Stack HCI now in public preview | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/azure-kubernetes-service-on-azure-stack-hci-now-in-public-preview/)
	- 2021/5/25にGA
		- [Azure Stack HCI の Azure Kubernetes Service (AKS) の一般提供が開始されました | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/azure-kubernetes-service-aks-on-azure-stack-hci-is-now-generally-available/)
- AKS on Windows Server
	- サポートされるのかされないのかあいまいな
- Windows
- Windows IoT

## WindowsおよびWindows IoT上のAKS
- AKS-IoT VMが動作する
	- PC1台につきMariner Linux VM 1台
	- インストール時に決定したRAM, ストレージ、CPUコア数が静的に制限される

## どんな環境でAKSが動くのか？
- Mariner Linux
	- Microsoftが開発するLinuxディストリビューション

[パブリック プレビュー:Azure Kubernetes Service ハイブリッド デプロイ オプション | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/public-preview-azure-kubernetes-service-hybrid-deployment-options/)


