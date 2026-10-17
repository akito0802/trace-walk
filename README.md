# TRACE — 散歩を、小さな冒険に。

GitHub Pagesで無料公開できる、スマホ向け散歩アプリの試作版（v0.1）。ディープネイビー×ゴールドのUIで、街歩きを記録できます。

## 公開手順

1. このリポジトリの **Settings → Pages** を開く。
2. **Build and deployment → Source** は **Deploy from a branch** を選ぶ。
3. **Branch: main**、フォルダは **/(root)** を選んで **Save**。
4. Actionsのデプロイ完了後、`https://akito0802.github.io/trace-walk/` を開く。

## 初期実装

- ホーム / 探索 / ミッション / 記録 / マイページ
- 散歩時間の目安・散歩テーマ
- Leaflet と OpenStreetMap 標準タイルによる道路地図
- GPSでの軌跡・距離・経過時間、停止・再開・終了
- 位置精度の低い地点・異常なジャンプ・長時間GPS断絶を距離計算から除外
- 発見メモ・カテゴリ・写真（サイズを縮小し端末内保存）
- 4種類のミッションとXP
- IndexedDBに散歩履歴を保存
- JSON形式のバックアップ・復元
- PWAの基本設定

## 運用上の注意

- 散歩履歴・写真はブラウザーの**端末内ストレージ**に保存します。サーバーやGitHubにはアップロードしません。ブラウザーのデータ消去・機種変更で失われる場合があるため、定期的なバックアップを推奨します。
- 画面ロック中やバックグラウンドではGPSの継続追跡を保証できません。
- 地図の閲覧にはインターネット接続が必要です。OpenStreetMap公式タイルは [Tile Usage Policy](https://operations.osmfoundation.org/policies/tiles/) を守り、事前取得や大量ダウンロードはしません。
- 位置情報の利用はブラウザーの許可が必要です。
- ルート自動生成・音声ガイド・外部スポット自動取得・クラウド同期は未実装です。
- まだ実機GPSの精度検証は済んでいません。歩く際は周囲の安全に注意してください。

## 技術

GitHub Pages / HTML / CSS / Vanilla JavaScript / IndexedDB / Geolocation API / Leaflet 1.9.4 / OpenStreetMap tiles / Web App Manifest / Service Worker。Node.jsやビルド工程・有料サービスは不要です。

このリポジトリ内の `index.html` がアプリ本体です。