.. _deploying:

Deploying
=========

Staging
-------

Currently deploying to staging is a multi-part process.

1. Make sure your ``AWS_ACCESS_KEY_ID`` and ``AWS_SECRET_ACCESS_KEY`` are exported or prepended to the deploy command.
2. Run the following from the app directory ``fab -A staging deploy``
3. SSH into ``staging.pentameter.org``
4. Go to app directory ``/home/ubuntu/pentameter``
5. Build and upload assets with ``fab staging_assets``

Production
----------

TBD
