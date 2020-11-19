# confluence
default port: 8090

## How to run with docker-compose

```
    docker-compose up -d
```

- default db(mysql5.7) configure:

```bash
    driver=mysql5.7+
    host=mysql-confluence
    port=3306
    db=confluence
    user=confluence
    passwd=123123
```

## How to run with docker

- start confluence

```
    docker run -p 8090:8090 -v confluence_conf:/var/confluence --name confluence-srv -e TZ='Asia/Shanghai' zouchengli/confluence
```
