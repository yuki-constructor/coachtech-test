# アプリケーション名
お問い合わせフォーム


## 環境構築

### ⓵リポジトリをクローン

以下のコマンドで、Git リポジトリをクローンします。

git clone git@github.com:yuki-constructor/coachtech-test.git


### ⓶.env ファイルの作成

以下のコマンドで、 .env.example を .env にコピーします。

cp .env.example .env


.env ファイルを開いて、以下の設定を変更します。

APP_TIMEZONE=Asia/Tokyo


APP_LOCALE=ja


DB_HOST=mysql

DB_PORT=3306

DDB_DATABASE=laravel_db

DB_USERNAME=laravel_user

DB_PASSWORD=laravel_pass


### ⓷Dockerコンテナのビルドと起動

以下のコマンドで、Dockerコンテナを起動します。

docker-compose up --build -d


### ⓸PHPコンテナ内にログイン

以下のコマンドで、PHPコンテナに接続します。

docker-compose exec php bash


### ⓹composerのインストール

以下のコマンドで、composerをインストールします。

composer install


### ⓺データベースのマイグレーション

以下のコマンドで、データベースをセットアップするために、マイグレーションを実行します。

php artisan migrate


### ⓻アプリケーションの動作確認

 http://localhost:8080 にアクセスすることで、phpMyAdminを確認できます。


### ⓼データベースのシーディング

***シーディングファイルが、２つあり、以下の順番で実行しないと、エラーとなります。***
以下のコマンドで、データベースにサンプルデータを挿入するためにシーディングを実行します。

1. php artisan db:seed --class=CategoriesTableSeede
r
2. php artisan db:seed --class=ContactsTableSeeder


### ⑨アプリケーションの動作確認

 http://localhost にアクセスすることで、アプリケーションが動作していることを確認できます。


## 使用技術(実行環境)
- Laravel Framework 11.3.2
- PHP 8.2 以上

## ER図
![ER図](https://github.com/user-attachments/assets/f64c5674-6d4e-445c-aaad-93b042ec3cd8)

## URL
- 開発環境：git@github.com:yuki-constructor/coachtech-test.git







