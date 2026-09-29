## テーブル定義書

#### productsテーブル

| カラム名 | データ型 | 制約 | 説明 |
|:---|:-------|:-----|:-----------|
| id | BIGINT | PRIMARY KEY, AUTO_INCREMENT | 商品を1件ずつ区別する番号 |
| name | VARCHAR(50) | NOT NULL | 商品の名前 |
| price | INTEGER | NOT NULL | 商品の値段（円） |
| description | TEXT | - | 商品の短い説明 |
| category | ENUM('drink','food') | NOT NULL | 商品の区分（ドリンク・フード） |
| is_available | BOOLEAN | NOT NULL, DEFAULT true | その日に売れるかどうか。売り切れたら false にする |
| created_at | TIMESTAMP | - | 商品登録された日時 |
| updated_at | TIMESTAMP | - | 商品情報が更新された日時 |

#### ordersテーブル

| カラム名 | データ型 | 制約 | 説明 |
|:---|:-------|:-----|:-----------|
| id | BIGINT | PRIMARY KEY, AUTO_INCREMENT | 注文を1件ずつ区別する番号 |
| order_number | VARCHAR(6) | NOT NULL, UNIQUE | 注文番号 |
| total_amount | INTEGER | NOT NULL | 一件の注文の合計金額 |
| status | VARCHAR(20) | NOT NULL | 受け取りの状態 |
| ordered_at | DATETIME | NOT NULL | 注文を受けた日時 |
| created_at | TIMESTAMP | - | 注文情報が登録された日時 |
| updated_at | TIMESTAMP | - | 注文情報が更新された日時 |

#### order_productテーブル

| カラム名 | データ型 | 制約 | 説明 |
|:---|:-------|:-----|:-----------|
| id | BIGINT | PRIMARY KEY, AUTO_INCREMENT | 明細を1件ずつ区別する番号 |
| order_id | BIGINT | NOT NULL, FOREIGN KEY | どの注文の明細か |
| product_id | BIGINT | NOT NULL, FOREIGN KEY | どの商品か |
| quantity | INTEGER | NOT NULL | 個数 |
| unit_price | INTEGER | NOT NULL | 1種類の商品の合計額（products.price × quantity） |
| created_at | TIMESTAMP | - | 投稿が登録された日時 |
| updated_at | TIMESTAMP | - | 投稿情報が更新された日時 |
