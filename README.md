# 【Pythonスクレイピング】旅行パッケージ価格データ自動取得スクリプト開発（API解析）
# 旅行パッケージ情報自動取得システム

## 概要
本プロジェクトは、指定条件（出発地・目的地・日付・施設名）に基づき、対象サイトから旅行パッケージ情報（最安値・便情報・プラン名等）を自動取得し、MongoDBへ保存するPythonスクリプトです。

APIエンドポイントを解析し、直接HTTPSリクエストを送信することで、高速かつ安定したデータ取得を実現しています。

---

## 主な機能
- 指定条件による検索（出発地 / 目的地 / 日付 / 施設名）
- 最安値または指定便の情報取得
- プラン情報（料金・便・プラン名等）の取得
- MongoDBへのデータ保存
- Excelファイルに基づくバッチ処理
- 定期実行（スケジューリング対応）
- Docker環境での実行対応

---

## 技術スタック
- Python 3.x
- requests / BeautifulSoup (bs4)
- MongoDB
- Docker
- pandas（Excel処理）
- cron / スケジューラー

---

## ディレクトリ構成
```

project/
├── config
├── src/
├── .env
├── .docker-compose.yml
├── Dockerfile
├── sample_output.json
├── requirements.txt
└── README.md


---

## セットアップ方法

### ① リポジトリ取得
```bash
git clone <repository-url>
cd project

### ② 環境変数設定

`.env` ファイルを作成し、MongoDB接続情報を設定してください。

```env
MONGO_URI=mongodb://localhost:27017
DB_NAME=travel_db
COLLECTION_NAME=plans
```

---

### ③ Dockerで実行（推奨）

```bash
docker build -t travel-scraper .
docker run --env-file .env travel-scraper
```

---

## 開発者

金本 卓弥




