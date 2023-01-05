Hybrid Azure Kubernetes Service。名称は揺れており、現在のドキュメントでは下記の表現も見られる。
- Azure Kubernetes Service (AKS) hybrid deployment options
- Azure Kubernetes Service(AKS)ハイブリッド展開オプション
- AKS hybrid

## AKSを動かせる場所が広がる話
- AKS on Azure Stack HCIはHybrid Azure Kubernetes Service
	- 2020/9/22にパブリックプレビュー
		- [Azure Kubernetes Service on Azure Stack HCI now in public preview | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/azure-kubernetes-service-on-azure-stack-hci-now-in-public-preview/)
	- 2021/5/25にGA
		- [Azure Stack HCI の Azure Kubernetes Service (AKS) の一般提供が開始されました | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/azure-kubernetes-service-aks-on-azure-stack-hci-is-now-generally-available/)
- AKS on Windows Server
	- サポートされるのかされないのか曖昧な状況が続いていたが、現在は明確にWindows Serverもサポートされることが記載されている。
		- [Windows Admin Center を使って Azure Kubernetes Service on Azure Stack HCI and Windows Server を設定するクイックスタート - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/setup#setting-up-an-azure-kubernetes-service-host)
		- [PowerShell を使用して Azure Stack HCI および Windows Server クラスター上に Kubernetes を設定する - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/kubernetes-walkthrough-powershell)
- Windows、Windows IoT
	- AKS-IoT VMが動作する
		- PC1台につきMariner Linux VM 1台
		- インストール時に決定したRAM, ストレージ、CPUコア数が静的に制限される

## 何がメリットなのか？
- オンプレミスのKubernetesクラスターの管理、デプロイ、保守が簡単になる。

### 管理、保守
- LinuxホストとWindowsホストの両方に対応
- アップグレード
- 証明書の自動ローテーション
- Azure Arcにネイティブで接続し、Azureから管理可能
	- Azure Portal経由でAKSクラスターに接続可能
	- GitOps, Azure Policy
	- SQL Managed Instance, PostgreSQL Hyperscale
- Azure AD認証
- Azure Defenderによるガバナンスとセキュリティ
- Azure Monitorによるログ記録と監視

### デプロイ
AKSでは重要なアドオンのセットアップやKubernetesクラスターの作成に使用できるウィザードを利用可能
- PowerShell
- Windows Admin Center
- Azure CLI(プレビュー)
- Azure Portal(プレビュー)
- Azure Resorce Managerテンプレート(プレビュー)

## SDN

## どんな環境でAKSが動くのか？
- Mariner Linux
	- Microsoftが開発するLinuxディストリビューション

[パブリック プレビュー:Azure Kubernetes Service ハイブリッド デプロイ オプション | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/public-preview-azure-kubernetes-service-hybrid-deployment-options/)


