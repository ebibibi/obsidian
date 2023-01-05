- WindowsおよびWindows IoTをメインターゲットとした軽量のAKS
	- Windows 10と11
	- IoT Enterprise, Enterprise, Pro
	- Windows Server
- Windows Server上でも動作する
- 2022/10/12にパブリックプレビューとなった
- 小売店や医療機関での展開などがメインの想定
- LinuxおよびWindowsワークロードの両方をサポートする
- Azure Arcにネイティブ対応し、Azureからの管理が可能
- もちろんAzure Arcに対応。
- Azure ArcはWindows IoT Enterpriseもサポートする。
	- WindowsのArcサポートのアナウンスは確認中…。
- k8sとk3sの両方に対応
- 2 vCPUと4GBのRAMで動作する
- KubernetesクラスタはHyper-Vで分離された仮想マシンで動作するためセキュアである
- ワーカーノード用のLinuxとWindowsのOSイメージはマイクロソフトが管理する
	- セキュリティ更新もマイクソフトがお


## 参考
- [New hybrid deployment options for AKS clusters from cloud to edge](https://techcommunity.microsoft.com/t5/azure-arc-blog/new-hybrid-deployment-options-for-aks-clusters-from-cloud-to/ba-p/3645410)
- [Site Unreachable](https://techcommunity.microsoft.com/t5/internet-of-things-blog/taking-azure-arc-and-kubernetes-to-the-edge/ba-p/3650599)