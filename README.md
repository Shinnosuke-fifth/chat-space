# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

## users テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique:true|
|email|string|null: false, unique: true|
|password|string|null: false|


### Association
- has_many :group_users
- has_many :groups, through: :group_users
- has_many :messages

## groups テーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|


### Association
- has_many :group_users
- has_many :users, through: :group_users
- has_many :messages

## group_users テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## message テーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
