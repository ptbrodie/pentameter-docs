.. _api:

API
===

Overview
--------

All endpoints are prepended with ``/api/`` and will respond with JSON back with everything under a top level ``data`` key::

    {
        "data": {
            ...
        }
    }

auth
----

``POST /api/auth/login`` Logs a user in.

``POST /api/auth/signup`` Registers a new user. Returns author.

``GET /api/auth/logout`` Logs a user out.

``POST /api/auth/forgot-password`` Sends 'forgot password' email.

``POST /api/auth/reset-password`` Resets a password, linked from forgot password email.

``GET /api/auth/email-confirmation`` Sends 'email confirmation' email.

``POST /api/auth/verify-email`` Verifies user's email, linked from email-confirmation email

author
------

``GET /api/author/<author_id>`` Get author.

``GET /api/author/<author_id>/poem`` Get all poems by author.

``GET /api/author/<author_id>/collections`` Get collections by author.

collection
----------
``GET /api/collection/<collection_id>``


me
--

``GET /api/me`` Get current user. Returns Author

``PUT /api/me`` Update current user. Returns Author

``DELETE /api/me``  Delete current user. Returns Author

``POST /api/me/poem``  Create a poem. Returns poem.

``GET /api/me/poem`` Get all current user's poems. Returns list of poems.

``GET /api/me/poem/<poem_id>`` Get one poem by current user. Returns poem.

``PUT /api/me/poem/<poem_id>``  Update poem. Returns poem.

``DELETE /api/me/poem/<poem_id>`` Delete poem. Returns poem.




Endpoints
---------

.. toctree::
    :maxdepth: 3

    auth
    author
    collection
    poem
