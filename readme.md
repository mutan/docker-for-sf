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
composer require mutan/docker-for-sf:dev-master
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
