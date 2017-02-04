.._quickref_api:

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

``GET /api/author/<author_id>/collection`` Get all collections by author.

``PUT /api/author/<author_id>/follower`` Follow author.

``DELETE /api/author/<author_id>follower`` Unfollow author.

Future: ``Get /api/author/list/list_id`` Get list of authors (e.g. featured). Returns list of authors.

collection
----------

``GET /api/collection/<collection_id>`` Get collection. Returns collection.

``GET /api/collection/<collection_id>/poem`` Get all poems in collection. Returns list of poems.

``GET /api/collection/<collection_id>/poem/<poem_id>`` Get poem in collection. Returns poem.

``PUT /api/collection/<collection_id>/follower`` Follow collection.

``DELETE /api/collection/<collection_id>follower`` Unfollow collection.

Future: ``GET /api/collection/list/<list_id>`` Get a list of collections (e.g. xmas). Returns List of collections.

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

``GET /api/me/collection`` Get all current user's collections. Returns list of Collections

``POST /api/me/collection`` Create a new collection. Returns collection.

``PUT /api/me/collection/<collection_id>`` Update a collection. Returns Collection.

``DELETE /api/me/collection/<collection_id>`` Update a collection. Returns collection.

``GET /api/me/collection/<collection_id>/poem`` Get all poems in collection. Returns list of poems

``PUT /api/me/collection/<collection_id>/poem`` Add poem to collection. Returns collection.

``DELETE /api/me/collection/<collection_id>/poem`` Remove poem from collection. Returns collection.

poem
----

``GET /api/poem/<poem_id>`` Get poem by id. Returns Poem.

Future: ``PUT /api/poem/<poem_id>/metric`` Increment a metric for the given poem.
