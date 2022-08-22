#テーブル設計

## usersテーブル

| Column             | Type    | Options       |
|------------------- |---------|---------------|
| name               | string  | null: false   |
| email              | string  | null: false   |
| encrypted_password | string  | null: false   |

## roomsテーブル
| Column  | Type    | Options     |
|---------|---------|-------------|
| name    | string  | null: false |

## room_users テーブル

| Column  | Type        | Options                         |
|---------| ----------  | --------------------------------|
| user    | references  | null: false, foreign_key: true  |
| room    | references  | null: false, foreign_key: true  |

### Association

- belongs_to :room
- belongs_to :user

## messages テーブル

| Column    | Type        | Options                        |
|-----------|-------------|------------------------------- |
| content   | string      |                                |
| user      | references  | null: false, foreign_key: true |
| room      | references  | null: false, foreign_key: true |

- belongs_to :room
- belongs_to :user
