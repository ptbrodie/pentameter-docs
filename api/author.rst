.. _author_api:

Author
======

- Pentameter users are called `authors`.
- Pentameter author endpoints are used to manage author-centered activity.
- All author endpoints begin with the prefix ``/api/author``.

All author endpoints will return json of the form::

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
- ``"poems"`` section will show ``is_published`` if and only if the owner of the poem is making the request.

Get author by ID
----------------

``GET /api/author/<author_id>``

Retrieve an author by system id::

    Returns: Author

    Method: GET

Get one collection by author
----------------------------

``GET /api/author/<author_id>/collection/<collection_id>``

Retrieve the specified collection by the specified author::

    Returns: Collection

    Method: GET

Get collections by author
-------------------------

``GET /api/author/<author_id>/collection``

Retrieve the specified author's public collections::

    Returns: List of Collections

    Method: GET


Get one poem by author
------------------

``GET /api/author/<author_id>/poem/<poem_id>``

Retrieve the specified poem by the specified author::

    Returns: Poem

    Method: GET

Get poems by author
------------------

``GET /api/author/<author_id>/poem``

Retrieve the specified author's published poems::

    Returns: List of Poems

    Method: GET
