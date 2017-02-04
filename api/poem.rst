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


get
---

``GET /api/poem/<poem_id>``

Returns a poem if it exists::

    Method: GET
    Content-Type: application/json
    Body: empty


increment metric
----------------

``PUT /api/poem/<poem_id>/metric``

Used to increment a metric for the given poem::

    Returns: Poem

    Method: PUT
    Content-Type: application/json
    Body: {
        "metric": "read"
    }

like
----

``PUT /api/poem/<poem_id>/like``

Current user like the specified poem::

    Returns: Poem
    Logged in: Required

    Method: PUT

unlike
----

``DELETE /api/poem/<poem_id>/like``

Current user like the specified poem::

    Returns: Poem
    Logged in: Required

    Method: PUT
