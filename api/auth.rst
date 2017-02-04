.. _auth_api:

Auth
====

All auth endpoints begin with the prefix ``/api/auth``

login
-----

``POST /api/auth/login``

Logs in an existing author::

    Returns: Author

    Method: POST
    Content-Type: application/json
    Body:
    {
        "email": "email@email.com",
        "password": "password"
    }

signup
------

``POST /api/auth/signup``

Registers and creates a new author::

    Returns: Author

    Method: POST
    Content-Type: application/json
    Body:
    {
        "email": "email@email.com",
        "firstname": "firstname",
        "lastname": "lastname",
        "password": "password"
    }

logout
------

``GET /api/auth/logout``

Logs an author out if they are logged in::

    Returns: Author

    Method: GET
    Content-Type: N/A
    Body: Empty

forgot password
---------------

``POST /api/auth/forgot-password``

Triggers a "forgot password" email to be sent to a specified email address::

    Returns: Author

    Method: POST
    Content-Type: application/json
    Body:
    {
        "email": "email@email.com",
    }

reset password
--------------

``POST /api/auth/reset-password``

Used to reset a password from a temporary sign-in link that was sent to the author through the ``forgot password`` endpoint::

    Returns: Author

    Method: POST
    Content-Type: application/json
    Body:
    {
        "token": "<Forgot Password Token>",
        "new_password": "password",
        "confirmed_password": "password"
    }

verify email
------------

``POST /api/auth/verify-email``

Used to verify a user's email after they have been sent a token URL to their email::

    Returns: Author

    Method: POST
    Content-Type: application/json
    Body:
    {
        "token": "<verify email token>"
    }

email confirmation
------------------

``GET /api/auth/email-confirmation``

Used to send an email to the email address the author signed up with with a temporary link that can be used to confirm that the email is real and is controlled by the author::

    Returns: Author

    Method: GET
    Content-Type: N/A
    Body: Empty
