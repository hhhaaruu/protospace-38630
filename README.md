#テーブル設計

##usersテーブル

| Column             | Type    | Option                              |
| ------------------ | ------- | ----------------------------------- |
| name               | string  | null: false                         |
| email              | string  | null: false, uniqueness: true       |
| encrypted_password | string  | null: false                         |
| profile            | text    | null:false                          |
| occupation         | text    | null:false                          |
| position           | text    | null:false                          |

###アソシエーション
- has_many :prototypes
- has_many :comments

##prototypesテーブル

| Column             | Type       | Option                                  |
| ------------------ | ---------- | --------------------------------------- |
| title              | string     | null: false                             |
| catch_copy         | text       | null: false                             |
| concept            | text       | null: false                             |
| user               | references | null: false, foreign_key: true          |

###アソシエーション
- belongs_to :user
- has_many :comments

##commentsテーブル

| Column             | Type       | Option                                  |
| ------------------ | ---------- | --------------------------------------- |
| content            | text       | null: false                             |
| prototype          | references | null: false, foreign_key :true          |
| user               | references | null: false, foreign_key :true          |

###アソシエーション
- belongs_to :user
- belongs_to :prototype

