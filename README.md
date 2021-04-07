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


## usersテーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| name      | string     | null: false |
| email     | string     | null: false |
| password  | string     | null: false |

### Association
- has_many :Purchases


## itemsテーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| item_name | string     | null: false |
| price     | integer    | null: false |
| image     | none       | none        |

### Association
- has_many :Purchases


## Purchasesテーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| id        | string     | null: false                    |
| name      | references | null: false, foreign_key: true |
| item_name | references | null: false, foreign_key: true |

### Association
- belong_to :users
- belong_to :items
- has_one :addresses


## addressesテーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| name    | string     | null: false                    |
| id      | references | null: false, foreign_key: true |
| address | references | null: false, foreign_key: true |

### Association
- belong_to :Purchases