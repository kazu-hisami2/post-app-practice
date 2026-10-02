# 投稿アプリ 構造表

| まとまり | 実物の場所 | 置くもの |
|:-----------|:---------------|:---------------|
| ルーティング | `routes/web.php` | どのURLが、どのコントローラーの何を呼ぶか。認証が必要かどうか |
| コントローラー | `app/Http/Controllers/PostController.php` | 受け取った内容をどう扱い、どの画面を返すか。どんな値まで受け付けるか |
| ポリシー | `app/Policies/PostPolicy.php` | 誰がその投稿を編集・削除してよいか |
| モデル | `app/Models/User.php`・`Category.php`・`Post.php` | データの読み書きと、テーブルどうしのつながり |
| モデル | `resources/views/posts/index.blade.php`・`edit.blade.php` | 画面に映すもの |
| データベース | `users`・`categories`・`posts`テーブル | 覚えておくデータ形式 |
