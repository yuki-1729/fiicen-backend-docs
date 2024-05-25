# カテゴリ: AUTH

## `POST` - `/signup/`
アカウントを作成します。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
### ヘッダー
- `Content-Type` - 使用されているのは `multipart/form-data`
- `X-Csrftoken` - クッキーと同様の値のCSRFトークン
### ペイロード(フォームデータ)
- `account_name` - 固有のアカウント名(他のアカウントと重複出来ない)
- `display_name` - 自由な表示名(他のアカウントと重複できる)
- `gender` - 性別(男: `1` | 女: `2` | 未設定: `9`)
- `g-recaptcha-response` - reCaptcha V3のレスポンス
### レスポンス
- `200 OK` - `{status: "success"}`
- `400 Bad Request` - HTMLが返されます
- `403 Forbidden` - HTMLが返されます(登録が全員制限されています)
- `500 Internal Server Error` - HTMLが返されます(負荷が高いときに発生するエラー)
### reCaptcha バイパス
JavaScriptを用いて、無制限にreCaptcha V3のレスポンスを取得できます。
```
grecaptcha.ready(function() {
  grecaptcha.execute('6LdK4OQpAAAAAGKQ1CmIu2g4TmbVBLdDWRlYA940', {action: 'submit'}).then(function(token) {
    console.log(token);
  });
});
```
Playwright Pythonを用いて自動的にバイパスを行うことも可能です。
```
async def solve():
  async with async_playwright() as playwright:
    chrome = playwright.chromium
    browser = await chrome.launch(headless=True)
    page = await browser.new_page()
    
    await page.goto("https://fiicen.jp/signup/")
    
    await page.evaluate("grecaptcha.ready(function() { grecaptcha.execute('6LdK4OQpAAAAAGKQ1CmIu2g4TmbVBLdDWRlYA940', {action: 'submit'}).then(function(token) { result = token; })});")
    await asyncio.sleep(1)
    solution = await page.evaluate("(function() {return result})")
    print(solution)

    await browser.close()
```

## `POST` - `/login/`
アカウントへログインします。
### クッキー
- `csrftoken` - 適当なページから取得したCSRFトークン
### ヘッダー
- `Content-Type` - 使用されているのは `application/x-www-form-urlencoded`
### ペイロード(フォームデータ)
- `csrfmiddlewaretoken` - `/login/` のGETリクエストのhtmlに含まれるCSRFトークン
- `account_name` - アカウントのユーザー名(固有ID)
- `password` - アカウントのパスワード
### レスポンス
- `200 OK` - HTMLが返されます(基本エラーですが、何故200にしてしまった?)
- `302 Found` - 応答なし(成功している場合は「`sessionid`」というクッキーが返されます)