=======================================================================================================================================================================================================
Setting up django to work with Postgres
=======================================================================================================================================================================================================

* Install psycopg2: 
  pip install psycopg2

* in your settings.py:
      DATABASES = {
        'default': {

            'ENGINE': 'django.db.backends.postgresql_psycopg2', # Add 'postgresql_psycopg2', 'mysql', 'sqlite3' or 'oracle'.

            'NAME': 'mydb',                      # Or path to database file if using sqlite3.
            # The following settings are not used with sqlite3:
            'USER': 'myuser',  # provide the existing user and password, if any

            'PASSWORD': 'password',

            'HOST': 'localhost',                      # Empty for localhost through domain sockets or           '127.0.0.1' for localhost through TCP.

            'PORT': '',                      # Set to empty string for default.
        }
    }


* run
  python manage.py syncdb
  to syncronize the database

* restart uwsgi

============================================================================================================================================================================================================
See more in section 8 of
https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-django-with-postgres-nginx-and-gunicorn
(we use uwsgi - gunicorn is similar)

