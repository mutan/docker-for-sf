## Installation

1. Add to `composer.json`:
```json
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/mutan/docker-for-sf.git",
        "reference": "master"
    }
]
```

2. Install package
```bash
composer require --dev mutan/docker-for-sf:^1.0
```

3. Make symlinks in project root dir
```bash
ln -s vendor/mutan/docker-for-sf/docker .
ln -s vendor/mutan/docker-for-sf/docker-compose.yml .
ln -s vendor/mutan/docker-for-sf/docker-compose.override.yml.dist docker-compose.override.yml
```

4. To avoid the problem when you can't change files made inside docker as root:
    * In `docker-compose.override.yml` replace YOUR_USERNAME_HERE by your actual username. You can get your username from bash by `echo "$USER"` or `whoami`.
    * Run commands inside containers as YOUR_USERNAME_HERE, not as root: `docker container exec -it -u YOUR_USERNAME_HERE app-php-fpm bash`
   

5. (optional) Update `.gitignore` in project root dir
```
###> mutan/docker-for-sf ###
docker
docker-compose.yml
docker-compose.override.yml
###< mutan/docker-for-sf ###
```

5. Run docker
```bash
docker-compose up -d --build
```

``localhost:8001`` your app  
``localhost:8002`` adminer  
``localhost:5001`` psql (connect from your local machine: ``psql -h localhost -p 5001 -U app``)  
``localhost:3001`` mysql (connect from your local machine: `mysql -h 127.0.0.1 -P 3001 -u app -p`)  

## Presentation

Изначально этот репозиторий был подготовлен как наглядное пособие для доклада на внутреннем митапе компании Shiptor.

Презентация: [Быстрое подключение Docker’а к вашему проекту на Symfony](https://docs.google.com/presentation/d/1kTtHikWRgdZ_3J2a_PY2tykS8TmB7ii7NVRMHCr9WBc/edit?usp=sharing)
