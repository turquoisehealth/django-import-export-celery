Install
=======

Install Python dependencies:

.. code-block:: bash

    cd example
    poetry install

Initialize database tables:

.. code-block:: bash

    poetry run python manage.py migrate

Create a super-user for the admin:

.. code-block:: bash

    poetry run python manage.py createsuperuser


Run
===

Start Redis (required for Celery):

.. code-block:: bash

    redis-server --daemonize yes

Start the Celery worker:

.. code-block:: bash

    poetry run celery -A project.celery worker -l info

Start the Django development server:

.. code-block:: bash

    poetry run python manage.py runserver

The example app will be available at http://127.0.0.1:8000/admin
