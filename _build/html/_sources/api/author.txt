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

get
---

``GET /api/author/<author_id>``

Retrieve an author by system id::

    Method: POST
    Content-Type: application/json
    Body:
    {
        "author_id": "author-system-id-0123"
    }

username
--------

``POST /api/author/username``

Retrieve an author by username::

    Method: POST
    Content-Type: application/json
    Body:
    {
        "username": "coolcat1999"
    }

signup
------

``POST /api/author/signup``

Registers and creates a new author::

    Method: POST
    Content-Type: application/json
    Body:
    {
        "email": "email@email.com",
        "firstname": "firstname",
        "lastname": "lastname",
        "password": "password"
    }

get
---

``GET /api/author/<author_id>``

Retrieves data for the specified author::

    Method: GET or POST
    Content-Type: application/json
    Body: Empty

login
-----

``POST /api/author/login``

Logs in an existing author::

    Method: POST
    Content-Type: application/json
    Body:
    {
        "email": "email@email.com",
        "password": "password"
    }

logout
------

``GET/POST /api/author/logout``

Logs a author out if they are logged in::

    Method: GET or POST
    Content-Type: N/A
    Body: Empty


is authorized
-------------

``GET /api/author/is-authorized``

Returns whether or not a author is logged in. author will be empty if not authorized::

    Method: GET
    Content-Type: N/A


forgot password
---------------

``POST /api/author/forgot-password``

Triggers a "forgot password" email to be sent to a specified email address::

    Method: POST
    Content-Type: application/json
    Body:
    {
        "email": "email@email.com",
    }

reset password
--------------

``POST /api/author/reset-password``

Used to reset a password from a temporary sign-in link that was sent to the author through the ``forgot password`` endpoint::

    Method: POST
    Content-Type: application/json
    Body:
    {
        "token": "<Forgot Password Token>",
        "new_password": "password",
        "confirmed_password": "password"
    }

email confirmation
------------------

``GET/POST /api/author/email-confirmation``

Used to send an email to the email address the author signed up with with a temporary link that can be used to confirm that the email is real and is controlled by the author::

    Method: GET or POST
    Content-Type: N/A
    Body: Empty

delete
------

``POST /api/author/delete``

Used to delete an existing author. Login is required::

    Method: POST
    Content-Type: application/json
    Body: Empty

photo
-----

``POST /api/author/photo```

Used to upload profile photos for the author::

    Method: POST
    Content-Type: multipart/form-data
    Body: Files keyed by name, e.g.:
    {
        'profile_banner_photo': ('mybanner.jpg', <data>, 'jpg'),
        'profile_photo': ('myphoto.png', <data>, 'png)
    }

update
------

``POST /api/author/update``

Used to update an author's settings::

    Method: POST
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
