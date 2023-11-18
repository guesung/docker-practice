# Docker Practice
## 1. Links
- [Docker Hub - Frontend](https://hub.docker.com/repository/docker/guesung/contacts-frontend/general)
- [Docker Hub - Backend](https://hub.docker.com/repository/docker/guesung/contacts-backend/general)  
- [Github](https://github.com/guesung/docker-practice)

## 2. Explanation

Explanation
This Docker practice project involves setting up a contacts application, which is split into three main components: the frontend, the backend, and the database. Each of these components is containerized using Docker, a platform that allows you to package applications into containers—standardized executable components combining application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.

## 2. Pre-requisites
1. docker cli
2. node.js (v18 or higher)
3. npm (v6 or higher)
4. git

## 3. How to run
### 3.1. Run the frontend
1. Clone this repository
```bash
git clone https://github.com/guesung/docker-practice.git
```
2. Move to the directory
```bash
cd docker-practice
```
3. Move to the frontend directory
```bash
cd frontend
```
4. Install dependencies
```bash
npm install
```
5. Build the Project
```bash
npm run build
```
> If you want to run the project in development mode, run the following command instead.
> ```bash
> npm run dev
> ```

> If you Counter an error, check your node version.
> ```bash
> node -v
> ```
> If your node version is lower than v18, update your node version.

6. Build the docker image
```bash
docker build -t contacts-frontend .
```
7. Run the docker image
```bash
docker run -d -p 3000:80 contacts-frontend
```

### 3.2. Run the backend
1. Move to the backend directory
```bash
cd ../backend
```
2. Install dependencies
```bash
npm install
```
3. Build the docker image
```bash
docker build -t contacts-backend .
```
4. Run the docker image
```bash
docker run -d -p 5000:5000 contacts-backend
```

### 3.3. Run the database
```bash
docker run --name mydatabase -dit -p 33306:3306 --net=contacts-network -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_DATABASE=contacts-mysql -e MYSQL_USER=contacts-mysql -e MYSQL_PASSWORD=123456 mysql --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci --default-authentication-plugin=mysql_native_password
```

