Poem Response
=============

All poem responses will take the form::

    {
       "data" : {
            "status_code": "<200 404 403 etc>",
            "message": "<message>",
            "poem": {
                "id": "asdf-asdf-adsf",
                "title": "Poem Title",
                "title_id": "poem-title",
                "year": 1999,
                "read_count": 12,
                "tags": ["birds", "sky", "venture capital"],
                "body": "<p>an html line of a poem. <br/><p>another line.",
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
                    "poems": [
                        "poem-id-1",
                        "poem-id-2",
                        "poem-id-3"
                    ]
                }
            }
       }
    }

- ``"poem"`` section will be an empty object if no poem found.
- An additional ``share_key`` will be present in responses from the ``/api/me/poem/`` endpoints.
  - This key can be used to retrieve poems using the ``/api/poem/private/<share_key>`` endpoint.


List of Poems
=============

A list of poems response will take the form::

    {
       "data" : {
            "status_code": "<200 404 403 etc>",
            "message": "<message>",
            "num_poems": 2
            "poems": [
                {
                    "id": "asdf-asdf-asdf",
                    "title": "The Knight",
                    "etc": "etc"
                },
                {
                    "id": "qwer-qwer-qwer",
                    "title": "The Rook",
                    "etc": "etc"
                }
            ]
       }
    }

