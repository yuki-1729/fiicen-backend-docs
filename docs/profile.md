# カテゴリ: PROFILE

## `POST` - `/settings/profile/`
アカウントのプロフィールを編集します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `icon` - アイコン画像(バイナリ)
- `display_name` - 表示名(他のアカウントとかぶってもOK)
- `introduce` - 自己紹介文
### レスポンス
- `200 OK` - 空のJsonが返されます(`{}`)

## `POST` - `/account/follow/`
他のアカウントをフォローします。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `followed_id` - フォローするアカウントのID
### レスポンス
- `200 OK` - `{"result": "followed"}`

## `POST` - `/account/mute/`
他のアカウントをミュートします。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `muted_id` - ミュートーするアカウントのID
### レスポンス
- `200 OK` - 空の応答が返されます