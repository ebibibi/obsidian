- Gitはバージョン管理システムの1つ。2005年に[[Linux]]の生みの親である[[リーナス・トーパルズ]]によってLinuxカーネルのソースコード管理のために開発された。
- Git以前のバージョン管理システムとして広く使われていた[[CVS]]や[[Subversion]]、Linuxカーネルのソースコード管理に使われていた[[BitKeeper]]等を事実上駆逐する勢いで普及した。

## Gitコマンド

### 初期設定
```
git config --global user.name "Masahiko Ebisuda"
git config --global user.email "ebibibi@gmail.com"
```

ローカルにリポジトリを作成しリモートにプッシュする
```
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/XX
```