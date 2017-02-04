.. _collection_api:

Collection
==========

All endpoints require an authenticated user.

new
---

``POST api/collection/new``

Create a new collection::

    Accept: application/json
    Content-Type: application/json
    Cookie: session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChKSKQ.ERr9S2vnshbo0VMD2Ohrrntq7qk
    Content-Type: application/json
    {"title": "baz", "description": "The baz collection", "tags": "temp, for example"}
     -- response --
    200 OK
    Server:  nginx/1.4.6 (Ubuntu)
    Date:  Tue, 10 May 2016 23:55:14 GMT
    Content-Type:  application/json
    Content-Length:  501
    Connection:  keep-alive
    Set-Cookie:  session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChQGYg.g5cLxbYULMcZIRu0iHYj6OGNIA8; HttpOnly; Path=/

    {
      "data": {
        "collection": {
          "author": "048d0a75-023c-4705-a483-9eff8cb7ed8f",
          "create_date": "2016-05-10T23:54:31.956597",
          "description": "The baz collection",
          "id": "53aa8968-077b-4781-a134-7e70afc79d7b",
          "is_public": null,
          "modify_date": "2016-05-10T23:55:14.267262",
          "poems": [],
          "tags": "temp, for example",
          "title": "baz"
        },
        "id": "53aa8968-077b-4781-a134-7e70afc79d7b",
        "message": "Collection",
        "status_code": 200
      }
    }

update
------

``PUT/PATCH api/collection/my-collection``

Update a collection::

    Accept: application/json
    Content-Type: application/json
    Cookie: session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChKSKQ.ERr9S2vnshbo0VMD2Ohrrntq7qk
    Content-Type: application/json
    {"title": "not-baz", "description": "This isn't the baz collection", "tags": "temp"}
     -- response --
    200 OK
    Server:  nginx/1.4.6 (Ubuntu)
    Date:  Wed, 11 May 2016 00:33:29 GMT
    Content-Type:  application/json
    Content-Length:  509
    Connection:  keep-alive
    Set-Cookie:  session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChQPWQ.a60tpcCzKLf0oKkxbzd2fEJyy_k; HttpOnly; Path=/

    {
      "data": {
        "collection": {
          "author": "048d0a75-023c-4705-a483-9eff8cb7ed8f",
          "create_date": "2016-05-10T23:54:31.956597",
          "description": "This isn't the baz collection",
          "id": "53aa8968-077b-4781-a134-7e70afc79d7b",
          "is_public": null,
          "modify_date": "2016-05-11T00:33:29.991084",
          "poems": [],
          "tags": "temp",
          "title": "not-baz"
        },
        "id": "53aa8968-077b-4781-a134-7e70afc79d7b",
        "message": "Collection found",
        "status_code": 200
      }
    }

all
---

``GET /api/collection/``

Get all collections for an authenticated user::

    Accept: application/json
    Content-Type: application/json
    Cookie: session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChKSKQ.ERr9S2vnshbo0VMD2Ohrrntq7qk

     -- response --
    200 OK
    Server:  nginx/1.4.6 (Ubuntu)
    Date:  Tue, 10 May 2016 00:38:47 GMT
    Content-Type:  application/json
    Content-Length:  398
    Connection:  keep-alive
    Set-Cookie:  session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChK_Fw.RkvrBZibfuZZlqvMmyujRmNw3To; HttpOnly; Path=/

    {
      "data": {
        "collections": [
          {
            "author": null,
            "create_date": "2016-05-09T23:25:37.093377",
            "id": "3678eedb-85d2-4018-88c3-303d2c6d1d92",
            "is_public": null,
            "modify_date": "2016-05-10T00:03:02.257568",
            "poems": [],
            "tags": null,
            "title": "Gore"
          }
        ],
        "message": "All Collections",
        "status_code": 200
      }
    }

get
---

``GET /api/collection/my-collection``

Get a collection for an authenticated user::

    Accept: application/json
    Content-Type: application/json
    Cookie: session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChKSKQ.ERr9S2vnshbo0VMD2Ohrrntq7qk

     -- response --
    200 OK
    Server:  nginx/1.4.6 (Ubuntu)
    Date:  Tue, 10 May 2016 00:47:36 GMT
    Content-Type:  application/json
    Content-Length:  1791
    Connection:  keep-alive
    Set-Cookie:  session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChLBKA.b0t3eW-3G66iIg-AX8Pb-6wiQlQ; HttpOnly; Path=/

    {
      "data": {
        "collection": {
          "author": null,
          "create_date": "2016-05-09T23:25:37.093377",
          "id": "3678eedb-85d2-4018-88c3-303d2c6d1d92",
          "is_public": null,
          "modify_date": "2016-05-10T00:47:11.525159",
          "poems": [
            {
              "author": {
                "bio": "This is chino's cool bio.",
                "birth_year": 1934,
                "death_year": null,
                "email": null,
                "firstname": null,
                "id": "f5e89dc3-7281-495c-99b4-a9177e927bd2",
                "lastname": null,
                "poems": [
                  "fa49a31a-4e5a-4b24-a7b1-40000de086f0"
                ],
                "profile_banner_url": null,
                "profile_photo_url": null,
                "username": "chino"
              },
              "body": "<p>\n In a circle of 12 winter trees\n <br/>\n I&rsquo;m hunched\n <br/>\n Remembering being fled from\n</p>\n<p>\n &mdash;Who gave me this wool sweater?\n <br/>\n So it please you life, we won&rsquo;t go alone&mdash;\n <br/>\n Next year will be better.\n <br/>\n Remember that white tree?\n</p>\n<p>\n The white underpaint of the government.\n <br/>\n The country of bone.\n</p>\n<p>\n <em>\n  In memory of Michael Brown\n </em>\n <br/>\n &nbsp;\n</p>\n",
              "create_date": "2016-05-06T21:02:17.668783",
              "feature_date": "2016-09-09T00:00:00",
              "id": "fa49a31a-4e5a-4b24-a7b1-40000de086f0",
              "modify_date": "2016-05-06T23:55:15.899121",
              "read_count": null,
              "tags": null,
              "title": "Poem from the Russian",
              "title_id": "poem-from-the-russian",
              "year": null
            }
          ],
          "tags": null,
          "title": "Gore"
        },
        "id": "3678eedb-85d2-4018-88c3-303d2c6d1d92",
        "message": "Collection",
        "status_code": 200
      }
    }

add poem
--------

``POST /api/collection/my-collection/poem/famous-poem``

Add a poem to a collection::

    Accept: application/json
    Content-Type: application/json
    Cookie: session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChKSKQ.ERr9S2vnshbo0VMD2Ohrrntq7qk
    Content-Type: application/json

     -- response --
    200 OK
    Server:  nginx/1.4.6 (Ubuntu)
    Date:  Tue, 10 May 2016 00:55:24 GMT
    Content-Type:  application/json
    Content-Length:  1791
    Connection:  keep-alive
    Set-Cookie:  session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChLC_A.YDori36mSmfQWAb3gzo3bsf4QtA; HttpOnly; Path=/

    {
      "data": {
        "collection": {
          "author": null,
          "create_date": "2016-05-09T23:25:37.093377",
          "id": "3678eedb-85d2-4018-88c3-303d2c6d1d92",
          "is_public": null,
          "modify_date": "2016-05-10T00:55:24.438087",
          "poems": [
            {
              "author": {
                "bio": "This is chino's cool bio.",
                "birth_year": 1934,
                "death_year": null,
                "email": null,
                "firstname": null,
                "id": "f5e89dc3-7281-495c-99b4-a9177e927bd2",
                "lastname": null,
                "poems": [
                  "fa49a31a-4e5a-4b24-a7b1-40000de086f0"
                ],
                "profile_banner_url": null,
                "profile_photo_url": null,
                "username": "chino"
              },
              "body": "<p>\n In a circle of 12 winter trees\n <br/>\n I&rsquo;m hunched\n <br/>\n Remembering being fled from\n</p>\n<p>\n &mdash;Who gave me this wool sweater?\n <br/>\n So it please you life, we won&rsquo;t go alone&mdash;\n <br/>\n Next year will be better.\n <br/>\n Remember that white tree?\n</p>\n<p>\n The white underpaint of the government.\n <br/>\n The country of bone.\n</p>\n<p>\n <em>\n  In memory of Michael Brown\n </em>\n <br/>\n &nbsp;\n</p>\n",
              "create_date": "2016-05-06T21:02:17.668783",
              "feature_date": "2016-09-09T00:00:00",
              "id": "fa49a31a-4e5a-4b24-a7b1-40000de086f0",
              "modify_date": "2016-05-06T23:55:15.899121",
              "read_count": null,
              "tags": null,
              "title": "Poem from the Russian",
              "title_id": "poem-from-the-russian",
              "year": null
            }
          ],
          "tags": null,
          "title": "Gore"
        },
        "id": "3678eedb-85d2-4018-88c3-303d2c6d1d92",
        "message": "Poem added",
        "status_code": 200
      }
    }

remove poem
-----------

``DELETE /api/collection/my-collection/poem/famous-poem/remove``

Remove a poem from a collection::

    Accept: application/json
    Content-Type: application/json
    Cookie: session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChKSKQ.ERr9S2vnshbo0VMD2Ohrrntq7qk

     -- response --
    200 OK
    Server:  nginx/1.4.6 (Ubuntu)
    Date:  Tue, 10 May 2016 01:38:38 GMT
    Content-Type:  application/json
    Content-Length:  412
    Connection:  keep-alive
    Set-Cookie:  session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChLNHg.DCK3D-hAQ3PYvamt8a9F5kNM1Hk; HttpOnly; Path=/

    {
      "data": {
        "collection": {
          "author": null,
          "create_date": "2016-05-09T23:25:37.093377",
          "id": "3678eedb-85d2-4018-88c3-303d2c6d1d92",
          "is_public": null,
          "modify_date": "2016-05-10T01:38:34.221338",
          "poems": [],
          "tags": null,
          "title": "Gore"
        },
        "id": "3678eedb-85d2-4018-88c3-303d2c6d1d92",
        "message": "Poem removed",
        "status_code": 200
      }
    }

remove
------

``DELETE /api/collection/my-collection/remove``

Remove a collection for an authenticated user::

    Accept: application/json
    Content-Type: application/json
    Cookie: session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChKSKQ.ERr9S2vnshbo0VMD2Ohrrntq7qk

     -- response --
    200 OK
    Server:  nginx/1.4.6 (Ubuntu)
    Date:  Tue, 10 May 2016 02:07:32 GMT
    Content-Type:  application/json
    Content-Length:  416
    Connection:  keep-alive
    Set-Cookie:  session=eyJfZnJlc2giOnRydWUsIl9pZCI6eyIgYiI6Ik1qRXpNVE00WlRFM09UVXlOVFZoTURkbVpETTJaalV3WkdZNVlXWTVaamM9In0sInVzZXJfaWQiOiIwNDhkMGE3NS0wMjNjLTQ3MDUtYTQ4My05ZWZmOGNiN2VkOGYifQ.ChLT5A.DUbIa_zsBETUoOr24oy_HDONrWQ; HttpOnly; Path=/

    {
      "data": {
        "collection": {
          "author": null,
          "create_date": "2016-05-10T02:04:12.739771",
          "id": "d1a8054a-dc8b-48c5-87cd-b5d455e274a4",
          "is_public": null,
          "modify_date": "2016-05-10T02:06:06.731052",
          "poems": [],
          "tags": null,
          "title": null
        },
        "id": "d1a8054a-dc8b-48c5-87cd-b5d455e274a4",
        "message": "Removed collection",
        "status_code": 200
      }
    }
