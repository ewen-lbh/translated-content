---
title: XMLHttpRequest.withCredentials
slug: Web/API/XMLHttpRequest/withCredentials
l10n:
  sourceCommit: b5b33acd44e7bb9c7be2efc75ba9a04b8bf8b2b2
---

{{APIRef('XMLHttpRequest')}}

**`XMLHttpRequest.withCredentials`** プロパティは論理値で、サイト間の `Access-Control` リクエストが Cookie、認証ヘッダー、 TLS クライアント証明書などの資格情報を使用して行うべきかどうかを示します。 `withCredentials` を設定しても、同じオリジンへのリクエストには影響しません。

さらに、このフラグは、レスポンスにおいて Cookie を無視すること示すためにも使われます。既定値は `false` です。異なるドメインからの `XMLHttpRequest` のレスポンスは、リクエストを行う前に `withCredentials` を `true` に設定しない限り、自身のドメインの Cookie 値を設定することができません。 `withCredentials` を true に設定することで得られるサードパーティの Cookie は、依然として same-origin ポリシーを尊重するので、リクエストスクリプトが [document.cookie](/ja/docs/Web/API/Document/cookie) やレスポンスヘッダーからアクセスすることはできません。

> **メモ:** これは同じオリジンへのリクエストには影響しません。

> **メモ:** 異なるドメインからの `XMLHttpRequest` レスポンスは、リクエストを行う前に `withCredentials` を `true` に設定しない限り、 `Access-Control-` ヘッダーの値にかかわらず、自ドメインの Cookie 値を設定*できません*。

## 値

論理値です。

## 例

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', 'http://example.com/', true);
xhr.withCredentials = true;
xhr.send(null);
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}
