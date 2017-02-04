.. _author_response_api:

Author Response
===============

All author responses take the form::

    {
       "data" : {
            "status_code": "<200 404 403 etc>",
            "message": "<message>",
            "author": {
                "firstname": "firstname",
                "lastname": "lastname",
                "username": "username",
                "fullname": "firstname lastname",
                "email": "email@email.com",
                "bio": "this is a bio.",
                "birth_year": "1900",
                "death_year": "1984",
                "profile_banner_url": "http://assets.pentameter.org/img/banner_url.jpg",
                "profile_photo_url": "http://assets.pentameter.org/img/photo_url.jpg",
                "poems_count": "2",
                "poems": [
                   { "is_published": "true", "id": "poem_id_1","title": "Poem Title 1", "body": "body with<br>html", "etc": "etc" },
                   { "is_published": "false", "id": "poem_id_2","title": "Poem Title 2", "body": "body with<br>html 2", "etc": "etc" }
                ],
                "collections_count": "1",
                "collections": [
                   { "is_public": "true", "id": "collection_id_1", "etc": "etc" }
                ]
            }
       }
    }

- ``"author"`` section will be an empty object if no author found.
- ``"email"`` and other personal data will only be shown from ``me/`` endpoints.
- ``"poems"`` section will show ``is_published`` if and only if the owner of the poem is making the request.


List of Author
==============

A list of authors response will take the form::

    {
       "data" : {
            "status_code": "<200 404 403 etc>",
            "message": "<message>",
            "num_authors": 3
            "authors": [
                {
                    "id": "asdf-asdf-asdf",
                    "firstname": "Renat",
                    "lastname": "etc"
                },
                {
                    "id": "qwer-qwer-qwer",
                    "firstname": "Lusha",
                    "etc": "etc"
                }
                {
                    "id": "qwer-qwer-qwer",
                    "firstname": "Dan",
                    "etc": "etc"
                }
            ]
       }

- No personal data will be returned in author objects.
