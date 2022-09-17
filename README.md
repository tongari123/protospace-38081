# README

# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| name               | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |

### Association

- has_many :prototypes テーブル
- has_many :commentsテーブル



## prototypes テーブル

| Column      | Type       | Options     |
| ----------- | ---------- | ----------- |
| title       | string     | null: false |
| catch_copy  | text       | null: false |
| concept     | text       | null: false |
| user        | references | null: false |


### Association

- belongs_to :user テーブル
- has_many :commentsテーブル


## commentsテーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| contents    | text       | null: false, foreign_key: true |
| prototype   | references | null: false                    |
| user        | references | null: false                    | 

### Association

- belongs_to :users テーブル
- belongs_to :commentsテーブル


