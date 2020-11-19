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
    docker run -p 8090:8090 -v confluence_home_data:/var/confluence --name confluence-srv -e TZ='Asia/Shanghai' zouchengli/confluence:crack
```

## How to hack confluence

```
docker exec confluence-srv java -jar /var/agent/atlassian-agent.jar \
    -p conf \
    -m chengli.zou@gmail.com \
    -n chengli.zou@gmail.com \
    -o http://localhost:8090 \
    -s copy-you-server-id
```

## How to hack confluence plugin

- .eg I want to use BigGantt plugin
1. Install BigGantt from confluence marketplace.
2. Find `App Key` of BigGantt is : `eu.softwareplant.biggantt`
3. Execute :

```
docker exec confluence-srv java -jar /var/agent/atlassian-agent.jar \
    -p eu.softwareplant.biggantt \
    -m chengli.zou@gmail.com \
    -n chengli.zou@gmail.com \
    -o http://localhost:8090 \
    -s copy-you-server-id
```

4. Paste your license 