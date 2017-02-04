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

Response Types
--------------

.. toctree::
    :maxdepth: 3

    Author <author_response>
    Collection <collection_response>
    Poem <poem_response>


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
