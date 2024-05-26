# カテゴリ: CIRCLE

## `POST` - `/circle/create/`
サークルを作成、または他人のサークルにリプライします。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ / 通常サークル)
- `contents` - サークル内容
- `vote_choices1` - 投票の選択肢の内容
- `vote_choices2` - 投票の選択肢の内容
- `attached_image` - アップロードする画像(バイナリ)
- `attached_video` - アップロードする動画(バイナリ)
### ペイロード(フォームデータ / リプライ)
- `contents` - サークル内容
- `circle_id` - リプライするサークルのID
### レスポンス
- `200 OK` - 空のJsonが返されます(`{}`)

## `POST` - `/circle/like/`
サークルにいいねを付けます。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード
- `circle_id` - いいねするサークルのID
### レスポンス
- `200 OK` - `{"result": "liked"}`

## `POST` - `/circle/refly/`
サークルをリフライします。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード
- `circle_id` - リフライするサークルのID
### レスポンス
- `200 OK` - `{"result": "reflown"}`

## `POST` - `/circle/fix/`
サークルを自分のプロフィールに固定します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード
- `circle_id` - 固定するサークルのID
### レスポンス
- `200 OK` - `{"result": "fixed"}`

## `POST` - `/report/circle/:circle/`
サークルを報告します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード
- `type` - 報告するタイプ
### タイプ Enum
- `harassment` - 嫌がらせ、いじめ
- `discrimination` - 差別的または攻撃的な内容
- `misinformation` - 誤った有害な情報
- `violence` - 暴力的な発言
- `privacy` - プライバシーの侵害
- `spoofing` - なりすまし
- `suicide` - 自殺や自傷行為
- `spam` - スパムまたは誤解を招く内容
- `sensitive` - センシティブまたは不快感のある内容
### レスポンス
- `200 OK` - 空のJsonが返されます(`{}`)