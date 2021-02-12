# アプリ名 task-32087

## 概要

- 挑戦や経験してみたいことを書き出し、管理することができる

## 作成背景

- 映画（最高の人生の見つけ方）を観て、私もやりたいことリストを書いてみたいと思い、リスト管理アプリを作成することにしました。挑戦や経験、それによってできる思い出が人生を豊にする１つの重要な要素であると考えるので、自分はどんな挑戦や経験をしたいのか考えるキッカケになると思います。そして、目に見える形でリストを書き出すことで達成しようという気持ちが強くなり、行動にも移しやすくなると考えています。

## DB設計

### usersテーブル

| Column             | Type     | Options      |
| ------------------ | -------- | ------------ |
| name               | string   | null: false  |
| encrypted_password | string   | null: false  |

#### Association

- has_many :lists

### listsテーブル

| Column                 | Type       | Options           |
| ---------------------- | ---------- | ----------------- |
| name                   | string     | null: false       |
| info                   | text       |                   |
| category_id            | integer    | null: false       |
| user                   | references | foreign_key: true |

#### Association

- belongs_to :user