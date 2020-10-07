# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# テーブル設計

## users テーブル

| Column             | Type   | Options                       |
| ------------------ | ------ | ------------------------------|
| nickname           | string | null: false                   |
| email              | string | null: false, default          |
| password           | string | null: false, default          |

### Association

- has_many :tweets
- has_many :comments

## tweets テーブル

| Column             | Type   | Options                       |
| ------------------ | ------ | ------------------------------|
| user_id            | string | null: false                   |
| text               | string | null: false                   |
| image              | text   | null: false                   |

### Association

- belongs_to :user
- has_many   :comments

## comments テーブル

| Column             | Type   | Options                       |
| ------------------ | ------ | ------------------------------|
| user_id            | integer| null: false                   |
| tweet_id           | integer| null: false                   |
| text               | text   | null: false                   |

### Association

- belongs_to :user
- belongs_to :tweet
