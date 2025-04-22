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

## users テーブル

| Column             | Type    | Options                        |
| ------------------ | ------- | ------------------------------ |
| nick_name          | string  | null: false                    |
| email              | string  | null: false, unique:true       |
| encrypted_password | string  | null: false                    |
| last_name          | string  | null: false                    |
| first_name         | string  | null: false                    |
| last_name_kana     | string  | null: false                    |
| first_name_kana    | string  | null: false                    |
| birth_year         | integer | null: false                    |
| birth_month        | integer | null: false                    |
| birth_day          | integer | null: false                    |


## Association

- has_many :items
- has_many :orders



## items テーブル

| Column                  | Type        | Options                        |
| ----------------------- | ----------- | ------------------------------ |
| item_name               | string      | null: false                    |
| item_description        | text        | null: false                    |
| item_category_id        | integer     | null: false                    |
| item_condition_id       | integer     | null: false                    |
| shipping_free_player_id | integer     | null: false                    |
| location_id             | integer     | null: false                    |
| days_to_ship_id         | integer     | null: false                    |
| price                   | integer     | null: false                    |
| profit                  | integer     | null: false                    |
| user                    | references  | null: false, foreign_key: true |


## Association

- has_many :comments
- has_one :order



## orders テーブル

| Column          | Type        | Options                        |
| ----------------| ----------- | ------------------------------ |
| postal_code     | integer     | null: false                    |
| prefecture      | integer     | null: false                    |
| city            | text        | null: false                    |
| address_line1   | text        | null: false                    |
| address_line2   | text        |                                |
| phone_number    | integer     | null: false                    |
| user            | references  | null: false, foreign_key: true |
| item            | references  | null: false, foreign_key: true |


### Association

- belongs_to :user
- belongs_to :item



