# テーブル設計

### usersテーブル

| Column              | Type    | Options                   |
| ------------------- | ------- | ------------------------- |
| email               | strings | null: false, unique: true |
| encrypted_password  | strings | null: false               |
| name                | strings | null: false               |
| profile             | text    | null: false               |
| occupation          | text    | null: false               |
| position            | text    | null: false               |

### Association
- has_many : prototypes
- has_many : comments

##prototypesテーブル

| Column     | Type      | Options                        |
| ---------- | --------- | ------------------------------ |
| tile       | strings   | null: false                    |
| catch_copy | text      | null: false                    |
| concept    | text      | null: false                    |
| user       | reference | null: false, foreign_key: true |

### Association
- has_many : comments
- belongs_to : users

##commentsテーブル

| Column    | Type      | Options                        |
| --------- | --------- | ------------------------------ |
| content   | text      | null: false                    |
| prototype | reference | null: false, foreign_key: true |
| user      | reference | null: false, foreign_key: true |

### Association
- belongs_to : prototypes
- belongs_to : users
