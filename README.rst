=======================
Openpolis Social Access
=======================

The social auth component we use at openpolis.

As of now, it is an empty django project, that can be used to add this feature to other projects.
It will become the single point of authentication to get into our services/api.

It uses both ``django_social_auth`` and ``django_registration``, to allow for oauth/oauth2 authentication
through facebook, twitter, google, and a standard regitration/activation workflow, to register as proper users.

To add social_auth features, you need to configure some environment variables and to add or modify settings
in the auth-providers' web sites.

Facebook
--------
FACEBOOK_APP_ID         = environ.get('FACEBOOK_APP_ID', '')
FACEBOOK_API_SECRET     = environ.get('FACEBOOK_API_SECRET', '')

* Go to https://developers.facebook.com/apps create a new web app and get the codes from there.
* Set ``App Domain`` to your 2nd level domain.
* Define ``Website with Facebook Login`` (but I don't know if it's really needed).


Twitter
-------
TWITTER_CONSUMER_KEY    = environ.get('TWITTER_CONSUMER_KEY', '')
TWITTER_CONSUMER_SECRET = environ.get('TWITTER_CONSUMER_SECRET', '')

* Go to https://dev.twitter.com/apps, create a new application or manage an existing one.
* Set the ``Callback URL``.
* Check the ``Allow this application to be used to Sign in with Twitter`` box.

Google
------
GOOGLE_OAUTH2_CLIENT_ID    = environ.get('GOOGLE_OAUTH2_CLIENT_ID', '')
GOOGLE_OAUTH2_CLIENT_SECRET    = environ.get('GOOGLE_OAUTH2_CLIENT_SECRET', '')


* Go to https://code.google.com/apis/console/, select API Access, create a new ``Client ID`` for web applications
* Set the ``Redirect URIs to http://DOMAIN/complete/google-oauth2/
* Get ``Client ID`` and ``Client secret``