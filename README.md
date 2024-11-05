# Docker Assignment - Agile Software Practice. 

__Name:__ Pawel Jaglarz

__Demo:__ https://youtu.be/QJy3MCal2dI



This repository contains the containerization of the multi-container application illustrated below.

![](./images/arch.png)


### Overview.
This project containerizes a multi-service application using Docker Compose. It includes:

Movies API: Provides access to movie data.
MongoDB: Stores the application’s data persistently.
Redis: Caches data for quick access.
Mongo Express: Web-based MongoDB management tool for development.


### Database Seeding
The MongoDB service is automatically seeded with initial data for testing and development. The data is loaded from a JSON file (seeding.json) and imported into MongoDB when the project starts.

The seeding process is managed by the mongodb-seed service, which runs the following command:

mongoimport --host mongodb --db movies_dbdocker --collection movies --authenticationDatabase admin --username ${MONGODB_USERNAME} --password ${MONGODB_PASSWORD} --drop --jsonArray --file /mongodb-init/seeding.json



### Multi-Stack
This Docker Compose setup supports both development and production configurations. For development, Mongo Express and MongoDB seeding are included. Production configuration excludes these services.
