# YaMDB
![workflow status](https://github.com/IuriyLeb/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

YaMDB is a service for creating reviews and comments to a different titles(books, movies, etc.).

Service is available via API

## Installation

Use the [DockerHub](https://hub.docker.com/) to download YaMDB image.

```bash
docker pull ileeb/api_yamdb:v0.1 
```
After download, you need to run image and set enviromental variables
```
docker run --env-file [.env file] ileeb/api_yamdb:v0.1
```
Then, make migrations, create superuser and collect static
```bash
docker-compose exec web python manage.py migrate
```
```bash
docker-compose exec web python manage.py createsuperuser
```
```bash
docker-compose exec web python manage.py collectstatic --no-input 
```

After all, the YaMDB project will be available in [localhost/api/v1/](http://localhost/api/v1/)
## Usage

YaMDB has pretty good documentation, built on ReDoc. You can access it on [localhost/redoc/](http://localhost/redoc/)

## More
### .env file structure
```dosini
DB_ENGINE
DB_NAME
POSTGRES_USER
POSTGRES_PASSWORD
DB_HOST
DB_PORT
SECRET_KEY
```

### About us
Author: [Lebeda Iuriy](https://github.com/IuriyLeb)

This project was done as a part of learning in [Yandex.Practicum](https://practicum.yandex.ru/) courses.

If you have any suggestions/comments, open pull requests or contact me by email.

### Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

### License
[MIT](https://choosealicense.com/licenses/mit/)
