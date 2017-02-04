.. _author_api:

Author
======

- Pentameter users are called `authors`.
- Pentameter author endpoints are used to manage author-centered activity.
- All author endpoints begin with the prefix ``/api/author``.

Get author by ID
----------------

``GET /api/author/<author_id>``

Retrieve an author by system id::

    Returns: Author Response

    Method: GET

Get one collection by author
----------------------------

``GET /api/author/<author_id>/collection/<collection_id>``

Retrieve the specified collection by the specified author::

    Returns: Collection Response

    Method: GET

Get collections by author
-------------------------

``GET /api/author/<author_id>/collection``

Retrieve the specified author's public collections::

    Returns: List of Collections Response

    Method: GET

Get one poem by author
------------------

``GET /api/author/<author_id>/poem/<poem_id>``

Retrieve the specified poem by the specified author::

    Returns: Poem Response

    Method: GET

Get poems by author
------------------

``GET /api/author/<author_id>/poem``

Retrieve the specified author's published poems::

    Returns: List of Poems Response

    Method: GET

Get author's followers
----------------------

``GET /api/author/<author_id>/follower``

Retrieve a list of followers for the given author::

    Returns: List of Authors Response

    Method: GET

follow
------

``PUT /api/author/<author_id>/follower``

Follow the given author::

    Returns: Author Response

    Method: PUT

Unfollow
--------
``DELETE /api/author/<author_id>/follower``

Unfollow the given author::

    Returns: Author Response

    Method: DELETE

Get list of authors
-------------------
``GET /api/author/list/<list_id>``

Get a list of authors (e.g. featured or top or by genre)::

    Returns: List of Authors Response

    Method: GET
