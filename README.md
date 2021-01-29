# テーブル設計

## usersテーブル

| Column             | Type     | Options      |
| ------------------ | -------- | ------------ |
| name               | string   | null: false  |
| encrypted_password | string   | null: false  |

### Association

- has_many :lists

## listsテーブル

| Column                 | Type       | Options           |
| ---------------------- | ---------- | ----------------- |
| name                   | string     | null: false       |
| info                   | text       |                   |
| category_id            | integer    | null: false       |
| user                   | references | foreign_key: true |

### Association

- belongs_to :user