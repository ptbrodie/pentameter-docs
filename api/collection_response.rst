Collection Response
===================

All collection responses will take the form::

    {
      "data": {
        "id": "53aa8968-077b-4781-a134-7e70afc79d7b",
        "message": "Collection",
        "status_code": 200
        "collection": {
          "author": "048d0a75-023c-4705-a483-9eff8cb7ed8f",
          "create_date": "2016-05-10T23:54:31.956597",
          "description": "The baz collection",
          "id": "53aa8968-077b-4781-a134-7e70afc79d7b",
          "is_public": null,
          "modify_date": "2016-05-10T23:55:14.267262",
          "poems": [],
          "tags": "temp, for example",
          "title": "baz"
        },
      }
    }

- ``"collection"`` field will be empty if nothing was found.

List of Collections
===================

A list of collections response will take the form::

    {
      "data": {
        "message": "List of Collections",
        "status_code": 200
        "num_collections": 3
        "collections": [
            {
                "id": "collection-id",
                "title": "collection-title",
                "author": "author-id",
                "poems": [
                    { "id": "asdf", "title": "You know", "etc": "etc"},
                    { "id": "asdf", "title": "etc"}
                ]
            },
            {
                "id": "collection-id",
                "title": "collection-title",
                "author": "author-id",
                "poems": [
                    { "id": "asdf", "title": "You know", "etc": "etc"},
                    { "id": "asdf", "title": "etc"}
                ]
            },
            {
                "id": "collection-id",
                "title": "collection-title",
                "author": "author-id",
                "poems": [
                    { "id": "asdf", "title": "You know", "etc": "etc"},
                    { "id": "asdf", "title": "etc"}
                ]
            }
        ]
      }
    }

