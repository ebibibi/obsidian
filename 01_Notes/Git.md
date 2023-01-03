- Gitはバージョン管理システムの1つ。2005年に[[Linux]]の生みの親である[[リーナス・トーパルズ]]によってLinuxカーネルのソースコード管理のために開発された。
- Git以前のバージョン管理システムとして広く使われていた[[CVS]]や[[Subversion]]、Linuxカーネルのソースコード管理に使われていた[[BitKeeper]]等を事実上駆逐する勢いで普及した。

## Gitコマンド

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
gi
```