## テーブル定義書

#### usersテーブル

| カラム名 | データ型 | 制約 | 説明 |
|:---|:-------|:-----|:-----------|
| id | BIGINT | PRIMARY KEY, AUTO_INCREMENT | ユーザーを1件ずつ区別する番号 |
| name | VARCHAR(255) | NOT NULL | ユーザーの名前 |
| email | VARCHAR(255) | NOT NULL, UNIQUE | ユーザーのメールアドレス |
| email_verified_at | TIMESTAMP | - | 有効なメールアドレスが登録された日時 |
| password | VARCHAR(255) | NOT NULL | ユーザーのパスワード |
| remember_token | VARCHAR(255) | - | 認証でパスワードを保持するときに発行されるトークン |
| created_at | TIMESTAMP | - | ユーザー登録された日時 |
| updated_at | TIMESTAMP | - | ユーザー情報が更新された日時 |

#### categoriesテーブル

| カラム名 | データ型 | 制約 | 説明 |
|:---|:-------|:-----|:-----------|
| id | BIGINT | PRIMARY KEY, AUTO_INCREMENT | カテゴリを1件ずつ区別する番号 |
| name | VARCHAR(255) | NOT NULL | カテゴリの名前 |
| created_at | TIMESTAMP | - | カテゴリ登録された日時 |
| updated_at | TIMESTAMP | - | カテゴリ情報が更新された日時 |

#### postsテーブル

| カラム名 | データ型 | 制約 | 説明 |
|:---|:-------|:-----|:-----------|
| id | BIGINT | PRIMARY KEY, AUTO_INCREMENT | 投稿を1件ずつ区別する番号 |
| user_id | BIGINT | NOT NULL, FOREIGN KEY | ユーザーを紐づける番号 |
| category_id | BIGINT | NOT NULL, FOREIGN KEY | カテゴリを紐づける番号 |
| title | VARCHAR(255) | NOT NULL | 投稿のタイトル |
| content | TEXT | NOT NULL | 投稿の本文 |
| created_at | TIMESTAMP | - | 投稿が登録された日時 |
| updated_at | TIMESTAMP | - | 投稿情報が更新された日時 |
