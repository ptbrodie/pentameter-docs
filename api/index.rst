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

Responses
---------

* Author Response
* Collection Response
* Poem Response
* List of Authors
* List of Collections
* List of Poems



Endpoints
---------

.. toctree::
    :maxdepth: 3

    quickref
    auth
    author
    collection
    me
    poem
