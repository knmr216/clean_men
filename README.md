# アプリケーション名
CleanMen

# アプリケーション概要
メンズ向けコスメクチコミアプリ

# URL

# テスト用アカウント

# 利用方法

# 目指した課題解決
- コスメの需要が高まってきた今、山のようにある商品の中から何を買えば良いか分からない人のために、自分に合った最高の商品を見つける手助けをする。

# 洗い出した要件
- ユーザー管理機能
- 商品登録機能
- 商品詳細表示機能
- クチコミ投稿機能
- マイページ機能

# 実装した機能についての動画と説明

# 実装予定の機能
- カテゴリ別表示機能
- マイフォルダ機能
- コメント機能
- いいね機能

# データベース設計

## usersテーブル
| Column             | Type    | Options                  |
| ------------------ | ------- | ------------------------ |
| nickname           | string  | null: false              |
| name               | string  | null: false              |
| email              | string  | null: false, unique:true |
| encrypted_password | string  | null: false              |
| age_id             | integer |                          |
| skin_quality_id    | integer |                          |
| introduction       | text    |                          |

### Association
- has_many :reviews

## itemsテーブル
| Column       | Type    | Options     |
| ------------ | ------- | ----------- |
| name         | string  | null: false |
| brand        | string  | null: false |
| category_id  | integer | null: false |
| capacity     | string  | null: false |
| price        | integer | null: false |
| introduction | text    | null: false |

### Association
- has_many :reviews

## reviewsテーブル
| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| star   | integer    | null: false                    |
| text   | text       | null: false                    |
| user   | references | null: false, foreign_key: true |
| item   | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :item

# ローカルでの動作方法