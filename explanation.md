## EXPLANATION :: 

### 1. Choice of the base image on which to build each container.
Chose the official node/alpine image because of the smaller size 


### 2. Dockerfile directives used in the creation and running of each container.
```
FROM : Initializes the build stage 
WORKDIR /app : changes the current working directory from / to /app
COPY package*.json ./ : Copies the package.json and add them to the file system of the container at that path
RUN npm install, RUN npm run build, execute any command in a new layer on top of the current image and commits the results during build execution.
COPY . . : copy the files from the Docker host to the filesystem 
EXPOSE : Indicates to Docker that the container will have a process listening on the given ports
CMD ["npm", "start", "build"] : Excecuted when the container is launched from the newly created image.

```
### 3 .Docker-compose Networking (Application port allocation and a bridge network implementation) where necessary.
Used a configured network to ensure the containers communicate to each other


### Running the application

To run the YOLO application using Docker Compose, follow these instructions: - Fork the repository at https://github.com/dancunkip/yolo - Clone the repository to your local machine using the command git clone https://github.com/[your-username]/yolo.git - Change into the yolo directory using the command cd yolo - Build the Docker images and start the containers by running sudo docker-compose up --build - The backend will be running on port 5000 and the frontend will be running on port 3000. You can access the application in your web browser at http://localhost:3000
