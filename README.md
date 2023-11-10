

## Mongodb docker 
mongodb docker-compose sample

 ``` yaml
services:
  mongo:
    image: mongo
    container_name: mongodb
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: example
    ports:
      - 27017:27017
 ```

## run widout docker 

 ``` 
export MONGODB_URI="mongodb://root:example@127.0.0.1:27017/"
export JWT_SECRET="testpass"
 ```

## Build the container
1. `https://github.com/gotorosso/EARDIS-back-end.git`
2. `cd EARDIS-back-end/`
3. `docker build -t eardis-api .` 

## Run the container  

 ```sh
docker run -it --name eardis-api\
    -p 3000:3000 \
    -e MONGODB_URI="mongodb://root:example@127.0.0.1:27017/" \
    -e JWT_SECRET="testpass" eardis-api
 ```

- MONGODB_URI is the mongodb uri
- JWT_SECRET is the password for the jwt token encryption and decryption
