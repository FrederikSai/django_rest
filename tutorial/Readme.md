# Create the project directory
mkdir tutorial
cd tutorial

# Create a virtualenv to isolate our package dependencies locally
virtualenv env
source env/bin/activate

# Install Django and Django REST framework into the virtualenv
pip install django
pip install djangorestframework

# Set up a new project with a single application
django-admin.py startproject tutorial .  # Note the trailing '.' character
cd tutorial
django-admin.py startapp quickstart
cd ..

# Now sync database for the first time:
python manage.py migrate
python manage.py createsuperuser --email admin@example.com --username admin

# email:admin@example.com
# username:admin
# password:password01

# Testing our API
python manage.py runserver
