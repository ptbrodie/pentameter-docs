.. _poem_api:

Poem
====

Pentameter poem endpoints are used to manage poem-centered activity.

All poem endpoints will return json of the form::

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
- An additional ``share_key`` will be present in responses from the ``/api/poem/<poem_id>/share`` endpoint.
  - This key can be used to retrieve poems using the ``/api/poem/<share_key>/private`` endpoint.


all
---

``GET /api/poem``

Return list of all poems owned by the current user.


get
---

``GET /api/poem/<title-id>``

Returns a poem if it exists::

    Method: GET
    Content-Type: application/json
    Body: empty


share
-----

``POST /api/poem/<share_key>/private``

Returns a poem that has NOT been published. This poem can be retrieved by a secret ``share_key`` that is retrieved using the ``/api/poem/<poem_id/share`` endpoint::

    Method: POST
    Content-Type: application/json
    Body: empty


create
------

``POST /api/poem/create``

Create a new poem::

    Logged in: Required
    Method: POST
    Content-Type: application/json
    Body: empty


update
------

``POST /api/poem/<poem_id>/save``

Save the poem corresponding to the given poem_id. Can only be accessed by the author of the poem::

    Logged in: Required
    Ownership: Required
    Method: POST
    Content-Type: application/json
    Body:
    {
       "tags": ["happy", "bird", "cloud"],
       "title": "A Poem Title",
       "body": "A poem body with html"
    }

publish
-------

``POST /api/poem/<poem_id>/publish``

Publish the poem corresponding to the given poem_id. This endpoint will implicitly ``save`` the poem in its current state. Can only be accessed by the author of the poem::

    Logged in: Required
    Ownership: Required
    Method: POST
    Content-Type: application/json
    Body:
    {
       "tags": ["happy", "bird", "cloud"],
       "title": "A Poem Title",
       "body": "A poem body with html"
    }

share
-----

``POST /api/poem/<poem_id>/share``

Get a ``share_key`` for the poem corresponding to the given ``poem_id``::


    Logged in: Required
    Ownership: Required
    Method: POST
    Content-Type: application/json
    Body: Empty

**This endpoint will return a json response identical to other poem endpoints, except with an added** ``share_key`` **value found in** ``data.poem.share_key``

delete
------

``POST /api/poem/<poem_id>/delete``

Delete the poem corresponding to the given ``poem_id``::

    Logged in: Required
    Ownership: Required
    Method: POST
    Content-Type: application/json
    Body: Empty


like
----

``GET /api/poem/<poem_id>/like``

Increment the like count for the poem corresponding to the given ``poem_id``::

    Logged in: Required
    Ownership: Not required
    Method: GET


read
----

``GET/POST /api/poem/<poem_id>/read``

Increment the read count for the poem corresponding to the given ``poem_id``::

    Logged in: Required
    Ownership: Not required
