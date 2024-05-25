# カテゴリ: SETTINGS

## `POST` - `/settings/publication_range/`
アカウントの公開範囲を編集します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `is_private` - フォロワーのみにするか(`0 = false` | `1 = true`)
### レスポンス
- `200 OK` - HTMLが返されます

## `POST` - `/settings/remove_follower/`
アカウントをフォローしている人を削除します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `contents_id` - フォローを削除するアカウントのID
### レスポンス
- `200 OK` - `{"status": "done"}`

## `POST` - `/settings/remove_follower/`
アカウントをフォローしている人を削除します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `contents_id` - フォローを削除するアカウントのID
### レスポンス
- `200 OK` - `{"status": "done"}`

## `POST` - `/api/generate_api_key/`
アカウントのAPIキーを生成(再生成)します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
無し(`{}`)
### レスポンス
- `200 OK` - `{"status": "Done."}`

## `POST` - `/settings/visual/`
アカウントのテーマ(表示モード)を変更します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `theme` - テーマを指定します(`light`: 白 | `dark`: 黒)
### レスポンス
- `200 OK` - HTMLが返されます

## `POST` - `/settings/languages/`
アカウントの言語を変更します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `language` - 言語を指定します(`ja`: 日本語 | `en`: 英語)
### レスポンス
- `200 OK` - HTMLが返されます