- 色々方法はありますが、このサイトは下記で構築されています。
	- https://github.com/ppeetteerrs/obsidian-zola
- 解説は書いてあるのでその通りにやってもらえばよいです…。

## 実装方法の概要とポイント
 - 該当のレポジトリをCloneして使う…のではなく自分の[[Obsidian]]のレポジトリをGitHubあたりに作ってそれを公開する形です。
 -  https://github.com/ppeetteerrs/obsidian-zola からnetlify.example.tomlをとってきて自分のレポジトリのルートにnetlify.tomlという名前で格納します。
 - netlifyでサイトを作り、自分のObsidianのレポジトリとリンクさせます。
 - netlify.tomlを編集し、自分のサイト向けの内容に書き換えます。
 - 私はnetlify.toml 内のLANDING_PAGEというオプションの設定方法で結構はまりました。
	 - このオプションではどこかレポジトリ内のmdファイルを指定してください。
	 - 自分のレポジトリのルートにindex.mdというファイルを作っては__いけません__。システム的に使うのでそれとバッティングしてしまいます。