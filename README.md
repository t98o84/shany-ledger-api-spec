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

## 自動バージョニング
mainブランチへのプッシュをトリガーにGitHub Actions が走り自動でバージョニングされるようになっいます。  
そのため、openapiのinfo.versionは手動更新不可となっています。
### マイクロバージョンアップ
通常のコミットの場合に現在のバージョンから+1したバージョンが設定されます。

### マイナーバージョンアップ
コミットのプレフィックスに「[openapi/minor]」が指定されていた場合に現在のバージョンから+1したバージョンが設定されます。

### マイナーバージョンアップ
コミットのプレフィックスに「[openapi/major]」が指定されていた場合に現在のバージョンから+1したバージョンが設定されます。
