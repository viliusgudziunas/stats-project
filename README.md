# Microservices with Docker, Flask and React

[![Build Status](https://travis-ci.com/viliusgudziunas/testdriven-app-tutorial.svg?branch=master)](https://travis-ci.com/viliusgudziunas/testdriven-app-tutorial)

## Command Line Commands For Deployment

### Bash Aliases

```
source ~/.bashrc
```

- dc='docker-compose'
- dm='docker-machine'

### Docker machines, containers and images

```
dm ls
docker container ls [-a]
docker image ls [-a]
```

### Docker Machine

```
eval $(dm env appname)
dm rm appname
dm create appname --driver virtualbox
dm restart appname
```

### Build docker containers

```
dc up -d --build
```

### Database

```
dc exec users python manage.py recreate_db
dc exec users python manage.py seed_db
dc exec users-db psql -U postgres
```

### Migrations

```
dc exec users python manage.py db init
dc exec users python manage.py db migrate
dc exec users python manage.py db upgrade
```

### Tests

```
dc exec users python manage.py test
dc exec users python manage.py cov
dc exec users flake8 . --exclude migrations
dc exec client npm test
dc exec client react-scripts test --coverage --watchAll=false
```

### Logs

```
dc logs -f
```
