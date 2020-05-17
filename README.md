# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :group_users
- has_many :groups,  through:  :group_users

## group テーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
|member|string|null: false|
|group_id|integer|null: false, foreign_key: true|

## Association
- has_many :posts
- has_many :group_users
- has_many  :users,  through:  :group_users


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|text|
|posts_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
