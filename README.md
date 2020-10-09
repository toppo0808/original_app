## userテーブル
| Colum              | Type     | Option      |
|--------------------|----------|-------------|
| name               |string    | null: false |
| email              |string    | null: false |
| password           |string    | null: false |

### Association
has_many: room_user
has_many: room, through: room_users
has_many: message

## memoテーブル
| Colum       | Type     | Option          |
|-------------|----------|-----------------|
|name         |string    | null: false     |

### Association
belongs_to: user
has_many: content


## memo_users テーブル
｜Colum   | Type       | Option                            |
|---------|------------|-----------------------------------|
| user_id | references | null: false, foreign_key: true    |
| room_id | references  | null: false, foreign_key: true   |

### Association

belongs_to :user
belongs_to :memo

## contentテーブル
| Colum   | Type     | Option                         |
|-------- |----------|--------------------------------|
| user_id | integer  | null: false, foreign_key: true |
| room_id | integer  | null: false, foreign_key: true |
| content | string   | null: false,                   |

### Association
belongs_to: user
belongs_to: memo
