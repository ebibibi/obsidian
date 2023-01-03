- Gitはバージョン管理システムの1つ。2005年に[[Linux]]の生みの親である[[リーナス・トーパルズ]]によってLinuxカーネルのソースコード管理のために開発された。
- Git以前のバージョン管理システムとして広く使われていた[[CVS]]や[[Subversion]]、Linuxカーネルのソースコード管理に使われていた[[BitKeeper]]等を事実上駆逐する勢いで普及した。

## なぜGitを使うのか？
- 複数人で同じディレクトリやファイル群に対して更新作業を行うと似たようなファイルが複数できてしまったりどのファイルが最新がわからなくなったり、最新のファイルを他人に上書きされてしまったりしてしまったりする。
- 問題が起きた時にもいつどのように問題が発生し、どのように元に戻せるのかもわからない。
- 「バージョン管理システムを使ってバージョン履歴を管理する」ことが解決策となる

## リポジトリで履歴を管理する
- Gitでは履歴を管理するために「り

## Gitコマンド例

### 初期設定
```
git config --global user.name "Masahiko Ebisuda"
git config --global user.email "ebibibi@gmail.com"
```

### ローカルにリポジトリを作成しリモートにプッシュする
```
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/XXXX/XXXX.git
git push -u origin master
```

### リモートからクローンする
```
git clone https://github.com/XXXX/XXXX.git
```

### リモートから変更を取得する
```
git pull
```

### リモートから変更を取得する
```
git fetch
git merge origin/master
```

### ファイルの登録(コミット対象を追加)
```
git add <ファイル名>
```

### ファイルの変更や追加をコミット
```
git commit -m "コミットメッセージ"
```

### ローカルの変更を確認する
```
git status
```

### リモートとローカルのファイルの差分を抽出する
```
git diff <ファイル名>
```

### commitの変更履歴を見る
```
git log
```

### 指定したcommitの変更点を見る
```
git show <コミットのハッシュ値>
```

### リモートにプッシュ
```
git push origin <ブランチ名>
```

### addの取り消し
```
git reset HEAD <ファイル名>
```

### commitの取り消し
```
git reset --hard HEAD^
```

commitの打ち消し
```
git revert <コミットのハッシュ値>
```

### コミットメッセージの修正
```
git commit --amend "新しいコミットメッセージ"
```

### pushの取り消し
```
git reset --hard <戻したいコミットのハッシュ値>
git push -f
```

### ローカルでブランチを作成
```
git branch <ブランチ名>
```

### ローカルでブランチを切り替え
```
git checkout <ブランチ名>
```

### ブランチ作成および切り替え
```
git checkout -b <ブランチ名>
```

### ブランチ名の変更
```
git branch -m <古いブランチ名> <新しいブランチ名>
```

### ブランチの削除
```
git branch -d <ブランチ名>
```

### ローカルのブランチをリモートに反映
```
git push -u origin <ローカルのブランチ名>
```

### リモートのブランチをローカルに持ってくる
```
git branch <ブランチ名> origin/<ブランチ名>
```

### リモートのブランチをローカルに持ってきたうえで切り替え
```
git checkout -b <ブランチ名> origin/<ブランチ名>
```

### 全てのブランチを確認する
```
bit branch -a
```

### ブランチ同士を比較する
```
git diff <ブランチ名> <ブランチ名>
```

### ブランチをマージする
```
git merge <ブランチ名>
```

### fast-forwardの関係であっても必ずマージコミットを作る
```
git merge --no-ff <ブランチ名>
```

### ブランチをリベースする
```
git rebase <ブランチ名>
```

### 変更点をいったん退避させる
```
git stash save
```

### 退避した作業の一覧を見る
```
git stash list
```

### 退避した作業を戻す
```
git stash apply <stash名>
```

### 退避した作業を消す
```
git stash drop <stash名>
```

### 退避した作業をすべて消す
```
git stash clear
```

### ファイル削除
```
git rm -f <ファイル名>
```

### ファイル名変更
```
git mv <元のファイル名> <新しいファイル名>
```

### ファイルを最新のコミットの状態に戻す
```
git checkout HEAD <ファイル名>
```

### ファイルを指定コミットまで戻す
```
git checkout <コミットのハッシュ値> <ファイル名>
```

### .gitignoreを無視して追加する
```
git add -f <ファイル名>
```

### ディレクトリだけ登録(.gitkeepをディレクトリに作成する)
```
touch <ディレクトリ名>/.gitkeep
```