## How to upgrade HAScO API?

1. Log into HAScO API hosting machine
2. Go to hascoapi folder: `cd /hascoapi`
3. Bring down hascoapi containers: `docker-compose down`
4. Delete current images and old containers: `docker-compose system prune -a`
5. Update current code: `git pull`
6. Restart hascoapi: `docker-compose up -d`
