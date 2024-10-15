## How to create HAScO API backup file?

In the example below, we named the backup file with the backup date. This can be any date and it may also include the time of the backup.

1. log into HAScO API hosting machine
2. Go to hascoapi folder: `cd /hascoapi`
3. Bring down hascoapi containers: `docker-compose down`
4. Go to home folder: `cd ~`
5. Generate the backup file: `docker run --rm --volumes-from hascoapi_fuseki -v $PWD:/bkp ubuntu bash -c "tar -zcvf /bkp/fuseki-data_BackupDate.tar.gz"`
6. Use `sftp` or `scp` to copy the backup file `/bkp/fuseki-data_BackupDate.tar.gz` out of the host machine.

## How to restore a HAScO API backup file?

1. Use `sftp` or `scp` to copy a backup file, e.g., `/bkp/fuseki-data_BackupDate.tar.gz` into the HAScO API host machine
2. Log into HAScO API hosting machine
3. Go to hascoapi folder: `cd /hascoapi`
4. Bring down hascoapi containers: `docker-compose down`
5. Go to home folder: `cd ~`
6. Restore the backup file: `docker run --rm --volumes-from hascoapi_fuseki -v $PWD:/bkp ubuntu bash -c "tar -zxvf /bkp/fuseki-data_BackupDate.tar.gz"`
