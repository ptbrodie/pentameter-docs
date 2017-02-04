.. _config:

Config
=======

Configuration for the app requires the environment is set up with variables that tell the app where to look for services, what credentials to use, or general settings to use::

    # Define the application directory
    import os
    BASE_DIR = os.path.abspath(os.path.dirname(__file__))

    PENTAMETER_ENV = os.getenv("PENTAMETER_ENV", "development")
    PENTAMETER_HOME = os.getenv("PENTAMETER_HOME", os.getenv("PYTHONPATH", os.getcwd()))

    SERVER_URL = os.getenv("SERVER_URL", "http://55.55.55.10")
    S3_BUCKET_NAME = None
    if PENTAMETER_ENV == "production":
        SERVER_URL = "https://pentameter.org"
        S3_BUCKET_NAME = "assets.pentameter.org"
    if PENTAMETER_ENV == "staging":
        S3_BUCKET_NAME = "assets.staging.pentameter.org"
        SERVER_URL = "http://staging.pentameter.org"
    if PENTAMETER_ENV == "development":
        S3_BUCKET_NAME = "assets.dev.pentameter.org"

    # Database
    POSTGRESQL_DATABASE_HOST = os.getenv("PENTAMETER_DBHOST", "127.0.0.1")
    POSTGRESQL_DATABASE_NAME = os.getenv("PENTAMETER_DBNAME", "pentameter")
    POSTGRESQL_DATABASE_USER = os.getenv("PENTAMETER_DBUSER", "pentameter")
    POSTGRESQL_DATABASE_PWD = os.getenv("PENTAMETER_DBPWD", "pentameter")
    SQLALCHEMY_DATABASE_URI = "postgresql://%s:%s@%s/%s" % \
                              (POSTGRESQL_DATABASE_USER,
                               POSTGRESQL_DATABASE_PWD,
                               POSTGRESQL_DATABASE_HOST,
                               POSTGRESQL_DATABASE_NAME)

    # Cache
    REDIS_HOST = os.getenv("PENTAMETER_REDISHOST", "127.0.0.1")
    REDIS_PORT = os.getenv("PENTAMETER_REDISPORT", 6379)
    REDIS_PWD = os.getenv("PENTAMETER_REDISPWD")
    REDIS_TIMEOUT = 3

    # EC2
    DEFAULT_EC2_REGION = "us-west-1"

    # Application threads. A common general assumption is
    # using 2 per available processor cores - to handle
    # incoming requests using one and performing background
    # operations using the other.
    THREADS_PER_PAGE = 1

    # Enable protection agains *Cross-site Request Forgery (CSRF)*
    CSRF_ENABLED = True

    # Use a secure, unique and absolutely secret key for
    # signing the data.
    CSRF_SESSION_KEY = os.getenv("CSRF_SESSION_KEY", "sosecret")

    PENTAMETER_SECRET_KEY = os.getenv("PENTAMETER_SECRET_KEY", "CHANGE_ME_BRO")
    PENTAMETER_PASSWORD_SALT = os.getenv("PENTAMETER_PASSWORD_SALT", "CHANGE_ME_PLEASE")

    ALGOLIA_APPLICATION_ID = os.getenv("ALGOLIA_APPLICATION_ID", "No Algolia ID Found")
    ALGOLIA_API_KEY = os.getenv("ALGOLIA_API_KEY", "No Algolia Key Found")
    MANDRILL_API_KEY = os.getenv("MANDRILL_API_KEY", "No Mandrill Key Found.")
    AWS_KEY = os.getenv("AWS_KEY", "No AWS Key Found.")
    AWS_SECRET = os.getenv("AWS_SECRET", "No AWS Secret Found.")

    POEM_SIMILARITY_THRESHOLD = 0.9

    PENTAMETER_TRANSACTIONAL_EMAIL = "email@pentameter.org"
    PENTAMETER_NOTIFY_EMAIL = "messenger@pentameter.org"
    PENTAMETER_RECOMMEND_EMAIL = "prophet@pentameter.org"

    STATIC_FOLDER = os.path.join(PENTAMETER_HOME, "pentameter/static")
