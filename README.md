# shanle-spec
ShanyLedgerのAPIスキーマ定義

## 規約
###  プロパティは特別な理由がない限りデータに含めない形で設計する。
参照：https://google.github.io/styleguide/jsoncstyleguide.xml?showone=Empty/Null_Property_Values#Empty/Null_Property_Values

### 新規作成のレスポンスは基本取得エンドポイントのレスポンスと同等のデータを返す

### リクエストとレスポンスボディのスキーマはschemas.ymlで定義し使用する

### レスポンスについて
新規作成:
  ステータス: 201
  特記事項: ヘッダーにLocationを含める

取得:
  ステータス: 200

更新:
  ステータス: 204

削除:
  ステータス: 204


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
