# shany-ledger-spec

ShanyLedgerのAPIスキーマ定義

## 環境構築
```shell
cd shany-ledger-api-spec
cp .env.example .env
touch spec/openapi.yml
docker compose up -d --build
```

## 変更の反映
`--build`オプションを指定しないと`docker-compose.yml`で設定している`command`が実行されないため指定している。
```shell
docker compose up -d --build
```
