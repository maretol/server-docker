# server-docker

サーバー上で起動しているDocker関連のあれこれをまとめているリポジトリ

何かあったらこのリポジトリをクローンして以下のものを立ち上げればいい感じに使える

# 起動するもの

## nginx / リバースプロキシ

サーバに各種パスでアクセスするといろんなやつにアクセスできるもの。鯖はドメインで叩かないと弾くようになってる。あっていればポート番号80と443ですべて事足りるようになる

Dockerコンテナ同士のネットワーク設定もこれに定義されているので一番最初にこれを起動させること

```
# project-root/compose/nginx で
$ docker compose up -d
```

## monitoring / 監視関係

docker compose でどちらも同時に起動するようになっている

```
# project-root/compose/monitoring で
$ docker compose up -d
```

### netdata

システム監視。生きてるかどうか

### dozzle

composeで動く環境のログビューア

# その他

## 環境変数

.env をプロジェクトルートに置くこと。シンボリックリンクですべての環境で .env のリンクがプロジェクトルートの .env を見るようになっている
パラメータは `.env.sample` を参照
