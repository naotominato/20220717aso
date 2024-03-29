# アプリケーション名：Rese（リーズ）
### ○飲食店予約サービス
#### 会員ユーザー向け予約システム
- ログイン後、【予約 / 予約変更 / 予約削除 / お気に入り店舗登録 / 評価 / QRコード認証 / 決済】などが可能
![スクリーンショット (51)](https://user-images.githubusercontent.com/103915849/189517514-0a5130e7-4b1b-4ab8-afdc-973976246f2e.png)
#### ログイン画面（ユーザ―用）
![スクリーンショット (54)](https://user-images.githubusercontent.com/103915849/189517556-0499265d-689a-4008-af8e-76ad0c87f92a.png)

### ○管理システム【管理者 / 各店舗代表者】
#### 【管理者】ログイン画面
- ログイン後、【既存店舗と紐づく"店舗代表者"の新規作成 / 新規店舗の立ち上げ】が可能
![スクリーンショット (53)](https://user-images.githubusercontent.com/103915849/189517493-cfa2ec55-665b-435d-ad88-5222b85637a6.png)
##### 【各店舗代表者】ログイン画面
- ログイン後、【担当店舗の予約状況確認 / 店舗情報 登録・更新 / お気に入り済みユーザーへのメール送信】が可能
![スクリーンショット (47)](https://user-images.githubusercontent.com/103915849/189517496-7b0d3822-bde7-4bf3-97ee-275cdfc4fcf8.png)

## 作成した目的：自社で予約サービスを持ちたい。
- 外部の飲食店予約サービスは手数料を取られるので自社での予約サービスを希望。

## 機能一覧
### ◎ユーザ―側
#### ○店舗一覧画面 (URL: / ) 
- 会員登録
- ログイン / ログアウト
- メール認証：　ユーザー登録後 → 初回ログイン時のみメール認証必要（※Mailtrap：テスト使用）
- 店舗一覧表示（店舗：条件検索あり）
- お気に入り店舗：　【登録 / 削除】【Home画面では、画面の更新をせずに切替が可能（非同期処理）】
- 店舗詳細ページ：　【店舗への予約可】
- Mypage： 【今後の予約確認： 一覧表示(日時順) / 予約変更 / 予約削除】　【お気に入り登録済み店舗：　一覧表示 / 削除】
- Mypage： 【当日の予約確認： 一覧表示(日時順) / QRコード発行 / 決済(Stripe： テスト使用)】
- Mypage： 【過去の予約確認： 一覧表示(日時順) / 店舗評価】
- リマインダー： 【予約当日09:00： 対象ユーザーへお知らせメール（自動送信）】（※Mailtrap：テスト使用）

### ◎管理画面
#### ○管理者側　(URL: /admin)
- ログイン / ログアウト
- 店舗代表者作成： 既存店舗と紐づけて登録　【作成済み店舗代表者一覧リストあり】
- 店舗の立ち上げ： 店舗名のみ作成可 【既存店舗情報の一覧リストあり】

#### ○店舗管理者側　(URL: /manager)
- ログイン / ログアウト
- 自店の予約一覧表示： 【当日 / 今後 / 過去】に分けて表示
- 自店の登録画面： 【地域 / ジャンル / 店舗説明文 / 店舗画像(storage上書き保存)】の 登録 / 更新　　その他【登録済み情報確認欄あり】
- メール送信： お気に入り登録済みのユーザー宛【一斉メールの送信可】（※Mailtrap：テスト使用）
- QRコードの認証： 来店のお客様から提示されるQRコードから【当日予約の照合】が可能（店舗代表者のログイン状態が必須 / 自店のみ照合可）

## 使用技術（実行環境）
- Laravel Framework 8.83.23
- jQuery 3.6.0 (CDN 経由)
- MySQL

## テーブル設計
![スクリーンショット (89)](https://user-images.githubusercontent.com/103915849/189526054-42abbc8c-e4bb-4b3c-899d-dc34cf305349.png)
![スクリーンショット (90)](https://user-images.githubusercontent.com/103915849/189526059-5d8beef0-abb8-4b83-bda6-c2957b46fd20.png)
![スクリーンショット (91)](https://user-images.githubusercontent.com/103915849/189526061-451556dc-df93-457d-8e3c-e9b7a2160f14.png)
![スクリーンショット (92)](https://user-images.githubusercontent.com/103915849/189526066-26230826-c023-4abe-8878-e0902b284a7a.png)
![スクリーンショット (93)](https://user-images.githubusercontent.com/103915849/189526070-96da49a6-b14d-42fd-8349-db02b1c895ba.png)
![スクリーンショット (95)](https://user-images.githubusercontent.com/103915849/189526074-6a64997c-ced8-410f-ac0f-345271c0d9b4.png)
![スクリーンショット (94)](https://user-images.githubusercontent.com/103915849/189526079-ab04f40f-5052-4d71-b251-b72545f94eb7.png)
![スクリーンショット (96)](https://user-images.githubusercontent.com/103915849/189526083-90935ba5-2629-41a3-aec6-513b1b135753.png)
![スクリーンショット (97)](https://user-images.githubusercontent.com/103915849/189526085-cfadc375-02d0-4faa-ad14-fd07e9c16184.png)

## ER図
![更新用er drawio](https://user-images.githubusercontent.com/103915849/189526179-dac44faa-2969-484b-bcb2-08473b969655.png)

# 環境構築
### 開発環境 構築コマンド　windows(コマンドプロンプト)の場合
- cd c:\xampp\htdocs
- git clone https://github.com/naotominato/rese.git
- cd rese
- composer install
- cp .env.example .env
- php artisan key:generate
- php artisan config:clear
- php artisan migrate
- php artisan db:seed
- php artisan storage:link
- php artisan serve
### .env（編集ファイル）
#### 変更点1
- DB_CONNECTION=mysql
- DB_HOST=127.0.0.1
- DB_PORT=3306
- DB_DATABASE=laravel ←任意のDBに変更
- DB_USERNAME=root　←使用者の設定に合わせる
- DB_PASSWORD=　←使用者の設定に合わせる
#### 変更点2 (Mailtrap使用の場合、下記の内容に変更）
- MAIL_MAILER=smtp
- MAIL_HOST=smtp.mailtrap.io
- MAIL_PORT=2525
- MAIL_USERNAME= ←Mailtrapのユーザー名
- MAIL_PASSWORD= ←Mailtrapのパスワード
- MAIL_ENCRYPTION=tls
- MAIL_FROM_ADDRESS=test@example.com
- MAIL_FROM_NAME="${APP_NAME}"
#### 変更点3（Stripe決済用　テストAPIキー　追記）
- STRIPE_KEY= ←Stripeの公開可能キー
- STRIPE_SECRET= ←Stripeのシークレットキー

### 開発環境　タスクスケジューラー　【予約当日】ユーザー向けメール自動送信（毎朝09:00）
- php artisan schedule:work　【メール自動送信開始コマンド（毎朝09:00設定中）】
- php artisan email:reserveduser　【手動確認コマンド（コマンド実施日の該当ユーザーへ即時送信）】

## その他
### ○アカウントの種類：　管理者 / 店舗代表者 / ユーザー
#### 下記、初期データ（各ログイン情報）
##### 管理者（１つのアカウントのみ）
- email:    admin@example.com
- password: 12345678
##### 店舗代表者（店舗：仙人）　←【店舗代表者側　動作確認テスト向き】
- email:    manager1@example.com
- password: 12345678
##### 店舗代表者（店舗：牛助）
- email:    manager2@example.com
- password: 12345678
##### テストユーザー1 　←【ユーザー側　動作確認テスト向き】
- email:    user1@example.com
- password : 12345678
##### テストユーザー2
- email:    user2@example.com
- password: 12345678
##### テストユーザー3
- email:    user3@example.com
- password: 12345678
