# 模擬案件（下書き用）
# アプリケーション名：Rese（リーズ）
### ○飲食店予約サービス
##### 会員ユーザーを対象とする予約システム
![スクリーンショット (22)](https://user-images.githubusercontent.com/103915849/179387425-a077edcc-b7b7-4772-8e12-3a95bbf71ef9.png)


### ○管理システム
##### 【管理者側、各店舗代表者側】各管理画面あり
###### ※下記、出力データは初期データです。

![スクリーンショット (20)](https://user-images.githubusercontent.com/103915849/179387324-5b446892-ed6e-4db3-b922-c1213dd80149.png)


## 作成した目的：自社で予約サービスを持ちたい。
- 外部の飲食店予約サービスは手数料を取られるので自社での予約サービスを希望。

## 機能一覧
### ◎ユーザ―側
#### ○店舗一覧画面 (URL: / ) 
- 会員登録
- ログイン / ログアウト
- 店舗一覧表示（条件検索あり）
- お気に入り店舗　【登録 / 削除】
- 店舗詳細画面あり（予約可）
- Mypage 予約【今後の予約確認 / 日時変更 / 削除 / 過去の予約確認 / 店舗評価 / 当日の予約確認 / QRコード発行 / 決済機能】
- Mypage お気に入り登録済み店舗 【一覧確認 / 削除】

### ◎管理画面
#### ○管理者側　(URL: /admin)
- ログイン / ログアウト
- 店舗の立ち上げ（店舗名のみ作成可）
- 既存店舗への店舗代表者登録
- 既存店舗情報の一覧表示
- 各店舗の店舗代表者一覧表

#### ○店舗管理者側　(URL: /manager)
- ログイン / ログアウト
- 自店の予約一覧表示：　当日 / 今後 / 過去を振り分け表示
- 自店の登録画面：　【地域 / ジャンル / 店舗説明文 / 店舗画像【登録 / 更新 / 登録済み情報確認】
- メール送信機能：　お気に入り登録済みのユーザー宛に一斉メールの送信可（Mailtrapを使用）
- QRコードの認証：　来店されたお客様から提示されたQRコードの照合が可能

## 使用技術（実行環境）
- Laravel Framework 8.83.23

## テーブル設計

![スクリーンショット (19)](https://user-images.githubusercontent.com/103915849/179387707-c5b62aec-3598-47f0-816e-dfa31945a2ce.png)

## ER図

![er drawio](https://user-images.githubusercontent.com/103915849/179387439-89e638e2-4719-447a-9f26-fab70e32e082.png)

# 環境構築
### ローカル環境構築コマンド　windows(コマンドプロンプト)の場合
- cd c:\xampp\htdocs
- git clone https://github.com/naotominato/rese.git
- cd rese
- composer install
- cp .env.example .env (.env内では、DB_DATABASE=　に任意のDBを配置）
- php artisan key:generate
- php artisan config:clear
- php artisan migrate
- php artisan db:seed
- php artisan serve

### ローカル環境　タスクスケジューラー　定期メール自動送信用コマンド（毎朝09:00）
- php artisan schedule:work

## その他
### ○アカウントの種類：　管理者 / 店舗代表者 / ユーザー
##### 管理者ログイン（１つのアカウントのみ）
- email:    admin@example.com
- password: 12345678
##### 店舗管理者ログイン（仙人）
- email:    user1@example.com
- password: 12345678
##### 店舗管理者ログイン（牛助）
- email:    manager1@example.com
- password: 12345678
##### 店舗管理者ログイン（戦慄）
- email:    manager1@example.com
- password: 12345678
##### ユーザーログイン（阿曽 直人）
- email:    user1@example.com
- password : 12345678
##### ユーザーログイン（あそ なおと）
- email:    user2@example.com
- password: 12345678
##### ユーザーログイン（アソ ナオト）
- email:    user3@example.com
- password: 12345678
