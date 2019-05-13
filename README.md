# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|body|text|null: false, foreign_key: true|
|image|string|foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## textテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|body|text|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## imageテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|image|string|foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
- has_many: texts, through: :photos_tags

## text_imageテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|body|text|null: false, foreign_key: true|
|image|string|foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, unique: true, foreign_key: true|
|name|text|null: false, unique: true, foreign_key: true|
|password|text|null: false, unique: true, foreign_key: true|
|email|text|null: false, unique: true, foreign_key: true|

### Association
- belongs_to :group
- has_many :messages

