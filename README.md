# PROFILES REST API

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)

## About <a name = "about"></a>

This is just a learning project, everything here is just an attempt to refresh the knowledge on Django.

## Getting Started <a name = "getting_started"></a>

### Prerequisites

- VirtualBox
- Vagrant

### Vagrant configuration

Run the below command to configure the development server

```
vagrant init ubuntu/bionic64
```

The contents of the Vagrantfile can be replaced with the one in this repository.

Then run the command in the current directory where the configuration file is present.

```
vagrant up
```

Once the vagrant box is started, we can connect to the vagrant server using vagrant ssh

```
vagrant ssh
```

### Creating a new Django project and app

Head to /vagrant dir in the vagrant server and run the below command to create a new project. It will create a manage.py file in root directory.


```
django-admin.py startproject profiles_project .
```

After creating the django project, we need to create a app within the project.
We will now use manage.py to create a new app.

```
python manage.py startapp profiles_api
```

### Enabling app in the django settings file

Open the root project(profiles_project) in this django project and open up settings.py file.
Update the installed apps as below:

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',
    'rest_framework.authtoken',
    'profiles_api',
]
```

### Running the django devlopment server

Run the below command in the vagrant server

```
python manage.py runserver 0.0.0.0:8000
```

The initial django page can be seen at 127.0.0.1:8000

## Usage <a name = "usage"></a>

- Create, update, delete & manage user profiles
- Authenticate with username and password
- Manage user profile feed items
