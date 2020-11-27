# テーブル設計

## users テーブル

| Column     | type    | options     |
| ---------- | ------- | ----------- |
| email      | string  | null: false |
| password   | string  | null: false |
| name       | string  | null: false |
| profile    | text    | null: false |
| occupation | text    | null: false |
| position   | text    | null: false |

### Association
- has_many :prototype
- has_many :comments

## prototype テーブル

| Column     | type       | options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | string     | null: false                    |
| concept    | string     | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many   :comments

## comments テーブル

| Column    | type       | options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :prototype