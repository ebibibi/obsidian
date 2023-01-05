- Azure Stack HCIおよびWindows Server上に展開可能なAKS
- WindowsおよびWindows IoT上に展開される軽量のAKSは[[AKS Edge Essentials]]と呼ばれ同じ[[Hybrid Azure Kubernetes Service]]ではあるが別物としてとらえるのがよさそう。

## 展開の前提条件
### [[Windows Admin Center]]を使用して展開する場合
- 展開には[[Windows Admin Center]]を使用するのが推奨とされている。[[Windows Admin Center]]を使う場合には下記の前提条件がある。
	- Azureに登録済みである必要がある
	- AKS展開先のAzure Stack HCIまたはWindows Serverと同じドメインに所属している必要がある
- Windows Admin Centerを使わずにPowerShellを用いて構築する方法もある

### AKSをホストするフェールオーバークラスター
- Azure Stack HCIあるいはWindows Server 2019/2022 Datacenterで構築されたフェールオーバークラスター
- クラスターのノード数は8以下であること(※Windows Serverとしてのフェールオーバークラスタの最大ノード数は64台。Storage Spaces Directとしての最大ノード数は16。)
- AKSの記憶域プールで1TB利用可能
- AKS VMの実行に30GB以上利用可能
- <span style="color: red">言語とリージョンはEN-USである必要がある</span>

## ネットワーク構成
- AKSで使用できクラスター上のVMからアクセスできる専用スコープのIPv4が必要

## 参考ドキュメント
- [Azure Kubernetes Service on Azure Stack HCI and Windows Server を使用したオンプレミスの Kubernetes とは - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/overview)