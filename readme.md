## Installation

1. Add to `composer.json`:
```json
"repositories": [
    {
        "type": "vcs",
        "url": "ssh://git@github.com:22/mutan/docker-for-sf.git",
        "reference": "master"
    }
]
```

2. Install package
```bash
composer require mutan/docker-for-sf:^1.0
```

3. Make symlinks in project root dir
```bash
ln -s vendor/mutan/docker-for-sf/docker-compose.yml .
ln -s vendor/mutan/docker-for-sf/docker .
```

4. (optional) Update `.gitignore` in project root dir
```
###> mutan/docker-for-sf ###
docker
docker-compose.yml
###< mutan/docker-for-sf ###
```

## Presentation

Изначально этот репозиторий был подготовлен как наглядное пособие для доклада на внутреннем митапе компании Shiptor.

Презентация: [Быстрое подключение Docker’а к вашему проекту на Symfony](https://docs.google.com/presentation/d/1kTtHikWRgdZ_3J2a_PY2tykS8TmB7ii7NVRMHCr9WBc/edit?usp=sharing)
