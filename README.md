# README

#userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|index: true,null: false,unique: true|
|email|string|null: false,unique: true|
- has_many :messages
- has_many :group through: :groups_users
- has_many :groups_users

#groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|index:true,null:false,unique:true|
- has_many :users through: :groups_users
- has_many :messages
- has_many :groups_users

#messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null:false|
|image|string||
|user_id|integer|null:false,foreign_key:true|
|group_id|integer|null:false,foreign_key:true|
- belongs_to :user
- belongs_to :group

#groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false,foreign_key:true|
|group_id|integer|null:false,foreign_key:true|
- belongs_to :user
- belongs_to :group