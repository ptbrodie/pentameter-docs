.. _collection_api:

Collection
==========

All endpoints require an authenticated user.

get
---

``GET /api/collection/<collection_id>``

Used to get a public collection by id::

    Returns: Collection Response

    Method: GET

get many poems in collection
----------------------

``GET /api/collection/<collection_id>/poem?author_id=<author_id>``

Used to get a subset of poems from the specified collection::

    Returns: List of Poems Response

    Method: GET
    URL Params:
        - author_id: an author's id
        - tags: future?

`NOTE`: No URL params returns all poems in collection

get one poem in collection
--------------------------

``GET /api/collection/<collection_id>/poem/<poem_id>``

Used to get the specified poem in the given collection::

    Returns: Poem Response

    Method: GET

follow
------

``PUT /api/collection/<collection_id>/follower``

Used to make the current user follow the collection::

    Returns: Collection Response

    Method: PUT
    Login: Required


unfollow
--------

``DELETE /api/collection/<collection_id>/follower``

Used to remove the current user from the collection's followers::

    Returns: Collection Response

    Method: DELETE
    Login: Required


get followers
-------------

``GET /api/collection/<collection_id>/follower``

Used to get a list of the collection's followers::

    Returns: List of Authors response

    Method: GET
