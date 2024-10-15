## How to refresh HAScO API's triplestore content?

1. Log into HAScO API hosting machine
2. Go to hascoapi folder: `cd /hascoapi`
3. Bring down hascoapi containers: `docker-compose down`
4. Delete triplestore volume: `docker volume rm hascoapi_hascoapi-fuseki-data`
5. Restart hascoapi: `docker-compose up -d`
