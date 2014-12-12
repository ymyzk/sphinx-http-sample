API
===

RESTful API のドキュメント.

.. http:get:: /users/(int:user_id)/books

   ユーザー (`user_id`) の書籍のリストを取得する API.

   **リクエスト例**

   .. sourcecode:: http

      GET /users/123/books HTTP/1.1
      Host: example.com
      Accept: application/json

   **レスポンス例**

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      [
        {
          "book_id": 123,
          "author_id": 35,
          "title": "Sphinx Book"
        },
        {
          "book_id": 125,
          "author_id": 13,
          "title": "Python Book"
        }
      ]

   :query sort: ``created_at`` または ``title``
   :query limit: 取得件数 (デフォルト: 10)
   :reqheader Authorization: OAuth のトークン (オプション)
   :statuscode 200: 成功
   :statuscode 404: ユーザーが見つからなかった

