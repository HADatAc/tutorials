## Installing HAScO API

1. HAScO API's host machine requires the installation of `git`. You can check it out [A.1. Installing `git`](https://github.com/HADatAc/hascoapi/wiki/A.1.-Installing-git);
2. Using `git clone`, clone HAScO API from github using the command: `git clone https://github.com/HADatAc/hascoapi.git`;
3. Edit `/hascoapi/conf/application.conf` and replace the variable `pac4.jwt.secret` value with another random string of around 40 characters. This JWT API token must be shared with the [rep application](https://github.com/HADatAc/rep).

## Running the HAScO API via Docker

1. HAScO API's host machine requires the installation of `docker`. You can check it out [A.2. Installing `docker`](https://github.com/HADatAc/hascoapi/wiki/A.2.-Installing-docker);
2. Access the cloned folder via terminal;
3. Type the command `docker build .`, to build HAScO API images;
4. Type the command `docker-compose up -d`, to run HAScO API;
5. Access http://localhost:9000 into a browser to access HAScO API dashboard.

## Running the HAScO API via Java compiler SBT

1. HASCOAPI's host machine requires the installation of Java 11 and `sbt`. You can check it out [A.3. Installing Java 11 and sbt](https://github.com/HADatAc/hascoapi/wiki/A.3.-Installing-Java-11-and-sbt);
2. Access the cloned folder via terminal;
3. Type `sbt`, to start sbt compiler bash;
4. Type `compile`, to compile the HASCOAPI java scripts;
5. Type `run`, to run the HAScO API;
6. Access http://localhost:9000 into a browser to access HAScO API dashboard.
