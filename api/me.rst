- Login is required for all endpoints.
- Me endpoints begin with ``/api/me``

get
---

``GET /api/me``

Used to get the current user's public and personal data::

    Returns: Author.

    Method: GET
    Content-Type: application/json

update
------

``PUT /api/me``

Used to update current user's settings::

    Returns: Author.

    Method: PUT
    Content-Type: application/json
    Body:
    {
        "firstname": "Lindsay",
        "lastname": "Lohan",
        "email": "lindsay@lohan.com",
        "username": "FreakyFriday",
        "bio": "This is lindsay's bio.",
        "password": "freaky-friday"
    }

`NOTE`: all parameters optional

photo
-----

``POST /api/me/photo```

Used to upload profile photos for the author::

    Method: POST
    Content-Type: multipart/form-data
    Body: Files keyed by name, e.g.:
    {
        'profile_banner_photo': ('mybanner.jpg', <data>, 'jpg'),
        'profile_photo': ('myphoto.png', <data>, 'png)
    }

delete
------

``DELETE /api/me``

Used to delete the current user::

    Returns: Author.

    Method: DELETE
    Body: Empty

create poem
-----------

``POST /api/me/poem``

Used to create a new poem with the current user as the author::

    Returns: Poem

    Method: POST
    Content-Type: application/json
    Body: Empty

get all poems
-------------

``GET /api/me/poem``

Used to retrieve all poems by the current user, public and private::

    Returns: List of Poems

    Method: GET

get poem
--------

``GET /api/me/poem/<poem_id>``

Used to get the specified poem::

    Returns: Poem

    Method: GET

update poem
-----------

``PUT /api/me/poem/<poem_id>``

Used to update the specified poem::

    Returns: Poem

    Method: POST
    Content-Type: application/json
    Body: {
        "tags": ['kittens', 'space', 'lusha'],
        "title": "Kittens in Space",
        "body": "A kitten in space<br>Lusha the astronaut"
        "is_published": true
    }

`NOTE`: is_published is optional. Set to true to publish. Set to false to unpublish.

delete
------

``DELETE /api/me/poem/<poem_id>``

Delete the specified poem::

    Returns: Poem

    Method: DELETE
    Body: Empty
