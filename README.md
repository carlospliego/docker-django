https://docs.docker.com/samples/django/

Create a Django project
`docker-compose run web django-admin startproject myApp .`

Connect the database
inside `settings.py` replace `DATABASES = ...` with the following:
```

# settings.py
   
import os
   
[...]
   
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ.get('POSTGRES_NAME'),
        'USER': os.environ.get('POSTGRES_USER'),
        'PASSWORD': os.environ.get('POSTGRES_PASSWORD'),
        'HOST': 'db',
        'PORT': 5432,
    }
}

```
