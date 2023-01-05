Hybrid Azure Kubernetes Service。名称は揺れており、現在のドキュメントでは下記の表現も見られる。
- Azure Kubernetes Service (AKS) hybrid deployment options
- Azure Kubernetes Service(AKS)ハイブリッド展開オプション
- AKS hybrid

実態としてはAzureの拡張機能に「hybridaks」やKubernetes用の拡張機能に「aks-hybrid-ext」というものがあり拡張機能に関連した事項かもしれない（推測）。

## 何が狙いで何がメリットなのか？
- オンプレミスのKubernetesクラスターの管理、デプロイ、保守が簡単になる。
- 全てのAKSクラスター(※Azure上でもオンプレミスでも他クラウドのマネージドKubernetesでも)に対して一貫したユーザーエクスペリエンスを提供する

## AKSを動かせる場所が広がる話
- [[AKS on Azure Stack HCI and Windows Server]]
	- AKS on Azure Stack HCI
		- 2020/9/22にパブリックプレビュー
			- [Azure Kubernetes Service on Azure Stack HCI now in public preview | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/azure-kubernetes-service-on-azure-stack-hci-now-in-public-preview/)
		- 2021/5/25にGA
			- [Azure Stack HCI の Azure Kubernetes Service (AKS) の一般提供が開始されました | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/azure-kubernetes-service-aks-on-azure-stack-hci-is-now-generally-available/)
	- AKS on Windows Server
		- サポートされるのかされないのか曖昧な状況が続いていたが、現在は明確にWindows Serverもサポートされることが記載されている。
			- [Windows Admin Center を使って Azure Kubernetes Service on Azure Stack HCI and Windows Server を設定するクイックスタート - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/setup#setting-up-an-azure-kubernetes-service-host)
			- [PowerShell を使用して Azure Stack HCI および Windows Server クラスター上に Kubernetes を設定する - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/kubernetes-walkthrough-powershell)
- [[AKS Edge Essentials]]
	- Windows、Windows IoT
		- AKS-IoT VMが動作する
			- PC1台につきMariner Linux VM 1台
			- インストール時に決定したRAM, ストレージ、CPUコア数が静的に制限される

## 展開の選択肢

|AKS ハイブリッドデプロイ オプション|ホスト OS|最小コンピューティング要件|フェールオーバー クラスタリングのサポート|AKS クラスター管理ツール|Azure Arc の統合|
|:--|:--|:--|:--|:--|:--|
|Windows Server 上の AKS|Windows Server 2019|メモリ: ノード|単一ノードまたは|ローカル PowerShell|Azure Arc の手動統合|
||Windows Server 2022|あたり 30 GB CPU コア: ノードあたり|2 から 8 ノードのフェールオーバー クラスター|Windows Admin Center||
|||16 ディスク領域: ノードあたり 128 GB||||
|Azure Stack HCI 上の AKS|Azure Stack HCI 21H2|メモリ: ノード|単一ノードまたは|ローカル PowerShell|Azure Arc の手動統合|
|||あたり 30 GB CPU コア: ノードあたり|2 から 8 ノードの Azure Stack HCI クラスター|Windows Admin Center||
|||16 ディスク領域: ノードあたり 128 GB||||
|[[Azure からの AKS クラスター プロビジョニング]] (プレビュー)|Windows Server 2019|メモリ: ノード|単一ノードまたは|Azure Portal|Azure Arc の自動統合|
||Windows Server 2022|あたり 32 GB CPU コア: ノードあたり|2 ノード クラスター|Azure CLI||
||Azure Stack HCI 21H2|16 ディスク領域: ノードあたり 128 GB||Azure Resource Manager テンプレート||
|[[AKS Edge Essentials]] (プレビュー)|Windows 10/11 IoT Enterprise|空きメモリ: > 2 GB|いいえ|ローカル PowerShell|Azure Arc の手動統合|
||Windows 10/11 Enterprise|CPU コア: 2||||
||Windows 10/11 Pro|クロック速度: 1.8 GHz||||
||Windows Server 2019/2022|空きディスク領域: 14 GB||||


### 管理、保守
- LinuxホストとWindowsホストの両方に対応
	- Linux, WindowsのOSを直接管理する必要なし
- [[Hybrid Azure Kuberntesのアップグレード]]
- 証明書の自動ローテーション
- Azure Arcにネイティブで接続し、Azureから管理可能
	- Azure Portal経由でAKSクラスターに接続可能
	- GitOps, Azure Policy
	- SQL Managed Instance, PostgreSQL Hyperscale
- Azure AD認証
- Azure Defenderによるガバナンスとセキュリティ
- Azure Monitorによるログ記録と監視
- Kubernetesノードプールの自動スケール

### デプロイ
AKSでは重要なアドオンのセットアップやKubernetesクラスターの作成に使用できるウィザードを利用可能
- PowerShell
- Windows Admin Center
- Azure CLI(プレビュー)
- Azure Portal(プレビュー)
- Azure Resorce Managerテンプレート(プレビュー)

### SDN
- AKS on Azure Stack HCIのSDN統合(プレビュー)を使用して仮想ネットワークにAKS-HCIノードをアタッチ可能。
- SND Software Load Balancerを用いてコンテナー化されたアプリケーションにロードバランサーサービスを提供可能

### GPU対応
- GPUパススルー(ディスクリートデバイス割り当て)を利用してNVIDIA Tesla T4 GPU上にGPU対応ノードプールをデプロイ可能

## どんなOSでAKSを動かしているのか？
- Mariner Linux
	- Microsoftが開発するLinuxディストリビューション

## 参考記事
- [パブリック プレビュー:Azure Kubernetes Service ハイブリッド デプロイ オプション | Azure の更新情報 | Microsoft Azure](https://azure.microsoft.com/ja-jp/updates/public-preview-azure-kubernetes-service-hybrid-deployment-options/)
- [Azure Kubernetes Service (AKS) ハイブリッド展開オプションのドキュメント | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/)
- [Azure からの AKS ハイブリッド クラスター プロビジョニングの概要 (プレビュー) - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/aks-hybrid-preview-overview)

