<<<<<<< HEAD
# emart-app
# EmartApp

A multi-service e-commerce application stack using Docker.

## Project Structure

- **client**: Angular frontend
- **nodeapi**: Node.js backend API
- **javaapi**: Java backend API
- **nginx**: Nginx reverse proxy configuration
- **emongo**: MongoDB database
- **emartdb**: MySQL database

## Running with Docker

### 1. Build Images

```sh
docker build -t client ./client
docker build -t api ./nodeapi
docker build -t webapi ./javaapi
```

### 2. Create Network

```sh
docker network create emartnet
```

### 3. Run Containers

```sh
docker run -d --name emongo --network emartnet -e MONGO_INITDB_DATABASE=epoc -p 27017:27017 mongo:4

docker run -d --name emartdb --network emartnet -e MYSQL_ROOT_PASSWORD=emartdbpass -e MYSQL_DATABASE=books -p 3306:3306 mysql:8.0.33

docker run -d --name nginx --network emartnet -p 80:80 -v %cd%\nginx\default.conf:/etc/nginx/conf.d/default.conf nginx:latest

docker run -d --name api --network emartnet -p 5000:5000 api

docker run -d --name webapi --network emartnet -p 9000:9000 webapi

docker run -d --name client --network emartnet -p 4200:4200 client
```

### 4. Access the Application

- Frontend: [http://localhost:4200](http://localhost:4200)
- Nginx (reverse proxy): [http://localhost](http://localhost)
- Node API: [http://localhost:5000](http://localhost:5000)
- Java API: [http://localhost:9000](http://localhost:9000)

## Stopping and Cleaning Up

```sh
docker stop client api webapi nginx emongo emartdb
docker rm client api webapi nginx emongo emartdb
docker network rm emartnet
```

## Notes

- Make sure you are in the `emartapp` directory when running these commands.
- Adjust volume paths for Windows if needed.
- Ensure Docker is running on your system.

---
```// filepath: c:\Users\shaha\OneDrive\Desktop\devops\emartapp\README.md
# EmartApp

A multi-service e-commerce application stack using Docker.

## Project Structure

- **client**: Angular frontend
- **nodeapi**: Node.js backend API
- **javaapi**: Java backend API
- **nginx**: Nginx reverse proxy configuration
- **emongo**: MongoDB database
- **emartdb**: MySQL database

## Running with Docker

### 1. Build Images

```sh
docker build -t client ./client
docker build -t api ./nodeapi
docker build -t webapi ./javaapi
```

### 2. Create Network

```sh
docker network create emartnet
```

### 3. Run Containers

```sh
docker run -d --name emongo --network emartnet -e MONGO_INITDB_DATABASE=epoc -p 27017:27017 mongo:4

docker run -d --name emartdb --network emartnet -e MYSQL_ROOT_PASSWORD=emartdbpass -e MYSQL_DATABASE=books -p 3306:3306 mysql:8.0.33

docker run -d --name nginx --network emartnet -p 80:80 -v %cd%\nginx\default.conf:/etc/nginx/conf.d/default.conf nginx:latest

docker run -d --name api --network emartnet -p 5000:5000 api

docker run -d --name webapi --network emartnet -p 9000:9000 webapi

docker run -d --name client --network emartnet -p 4200:4200 client
```

### 4. Access the Application

- Frontend: [http://localhost:4200](http://localhost:4200)
- Nginx (reverse proxy): [http://localhost](http://localhost)
- Node API: [http://localhost:5000](http://localhost:5000)
- Java API: [http://localhost:9000](http://localhost:9000)

## Stopping and Cleaning Up

```sh
docker stop client api webapi nginx emongo emartdb
docker rm client api webapi nginx emongo emartdb
docker network rm emartnet
```

## Notes

- Make sure you are in the `emartapp` directory when running these commands.
- Adjust volume paths for Windows if needed.
- Ensure Docker is running on your system.

---
=======
# docker-assignment-
>>>>>>> b3acac3817efb2cff9145077454d3fe61bd21ec1
