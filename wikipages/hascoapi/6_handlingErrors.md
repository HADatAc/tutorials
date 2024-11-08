# Handling errors

## Docker containers

### 1. Error response from daemon

#### 1.1 Cannot stop container

It would be best to type the command `sudo systemctl restart docker.socket docker.service` and then try executing the `docker stop containername` again.

## HAScO API

### 1. CreationException

#### 1.1. Unable to create injector, see the following errors

**Screenshots**
    ![Screenshot from 2024-10-11 11-14-14](https://github.com/user-attachments/assets/3658db01-39e4-4bdf-98c2-48031bec5d7c)
    ![Screenshot from 2024-10-11 11-13-00](https://github.com/user-attachments/assets/60cbcb7c-10b1-4bb3-a204-7ea54853659b)

**Cause**

Problem with the fuseki triplestore, commonly located at [http://localhost:3030](http://localhost:3030).

**Solutions**

First of all, you need to know if fuseki is active. To do this, run the `docker ps` command and check that the **hascoapi_fuseki** container is “Up”. In this case, there are a few possible scenarios:

1. **hascoapi_fuseki** does not appear in the list of containers

   If the **hascoapi_fuseki** container does not appear in the list of active containers, you need to run the following command:

   ```bash
   cd hascoapi_root
   docker compose up -d
   ```
2. **hascoapi_fuseki** is active but “Restarting” every time

   You need to change the permission of the files in the **./fuseki/** folder into HAScO API root. To do this, you can run the following command:

   ```bash
   cd hascoapi_root
   sudo chmod -R 777 ./fuseki/*
   ```
3. Port 3030 is already in use
   
   You need check the port usage with the following command
   ```bash
   sudo lsof -i :3030 
   ```
   and kill these PIDs typing the command
   ```bash
   sudo kill <type the PID>
   ```
   Or you can make it automatically
   ```bash
   sudo kill $(sudo lsof -i :3030 | grep :3030 | awk '{print $2}')
   ```
