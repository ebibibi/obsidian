## 現時点でできる操作
-  AKS ハイブリッド プレビュー クラスターの作成/一覧表示/表示
-  Azure RBAC を使用して、AKS ハイブリッド クラスター、ノードプール、vnet オブジェクトなどの Azure Resource Manager リソースへのアクセス権をユーザーに付与する
-  kubectl と Azure AD ID を使用して AKS ハイブリッド クラスターにアクセスする
-  AKS ハイブリッド クラスターに Linux ノードプールと Windows ノードプールを追加/一覧表示/表示する
-  AKS ハイブリッド クラスターとノードプールを削除する

## Azure Arcと連携して使用できるサービス
-  Azure Defender
-  GitOps v2
-  オープンサービスメッシュ
-  Azure Key Vault

## 前提条件
- AKSホスト管理クラスター
	- AKSホスト管理クラスター自体をAzureからプロビジョニングできるわけではない
- Azure Arcリソースブリッジ
- Azure Arc Kubernetesクラスター拡張機能
- カスタムの場所


## 参考
- [Azure からの AKS ハイブリッド クラスター プロビジョニングの概要 (プレビュー) - AKS hybrid | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/aks/hybrid/aks-hybrid-preview-overview)