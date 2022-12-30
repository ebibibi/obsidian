
## login
docker login [SERVER]

## pull image
docker pull image:TAG

# イメージからコンテナのコンソールを実行

docker images

docker run --rm -it <イメージID> /bin/bash

## Push

ローカルのイメージに対してリモートのタグをつける。そのうえでプッシュする。

docker tag kintone2haihai:latest asdfasdfasdfasdfaseee.azurecr.io/kintone2haihai:latest

docker push asdfasdfasdfasdfaseee.azurecr.io/kintone2haihai:latest

# Dockerfileのビルド

docker build . -t タグ

# イメージのリスト表示

docker images

# コンテナのリストおよび状態を表示

docker ps -a

# コンテナの起動(イメージからコンテナを作成して実行する)

docker run <imageid>

# -it インタラクティブにbashを実行

docker run -it <imageid> /bin/bash

# -d コンテナをバックグラウンドで起動

docker run -d <imageid> <command>

# -v コンテナに実行ホストのディレクトリをマウント

docker run -v /root/src/:/src <imageid>

docker run -v c:/tmp:/wintmp <imageid>

# -p ホストとコンテナのTCPポートのマッピング

下記はホストの8888ポートにアクセスするとコンテナの8080ポートにアクセスするように構成する例

docker run -o 8888:8080 <imageid>