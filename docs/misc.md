# カテゴリ: MISC

## `GET` - `/notification/`
通知をHTML形式で取得します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### レスポンス
- `200 OK` - HTMLが返されます

## `GET` - `/circle/block/topic/1/`
「話題」タブのサークルを取得します
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### レスポンス
- `200 OK` - HTMLが返されます

## `GET` - `/explore/trending/`
「トレンド」タブのハッシュタグトレンドをHTMLで取得します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### レスポンス
- `200 OK` - HTMLが返されます

## `GET` - `/circle/block/new/1/`
「最新」タブのサークルを取得します
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### レスポンス
- `200 OK` - HTMLが返されます

## `GET` - `/explore/trending/`
「トレンド」タブのハッシュタグトレンドをHTMLで取得します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### レスポンス
- `200 OK` - HTMLが返されます

## `GET` - `/explore/keywords/:word/`
トレンド検索のワードの補完を取得します
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
- `sessionid` - アカウントの有効なトークン
### レスポンス
- `200 OK` - 例(`[{"keyword": "word1"}, {"keyword": "word2"}]`)