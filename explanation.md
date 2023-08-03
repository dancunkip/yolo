## Docker Configration
The document entails  images, Dockerfile directives, networking, volume usag
### Ansible playgroup


### 1. Choice of the base image on which to build each container.
Chose the official node/alpine image because of the smaller size 

### 2. Installation /Prerequisites

Install the Below and make sure they are up

NB: Check the correct versions
   1. VirtualBox: Install VirtualBox from https://www.virtualbox.org/.
    2. Vagrant: Download and install Vagrant from https://www.vagrantup.com/.
   3. Ansible: Install Ansible using your package manager or pip.

## Vagrant configuration
it will will be configured Using Ansible to Provision Vagrant for Docker 

In the root directory intialize vagrant using vagrant init which creates a Vagrantfile 


##  Vagrant file
Add a vagrant file and add the ports requiredfor and initialize roles using the below command
```
      ansible-galaxy init <roleName>
```

And now you can run the playbook with ```
vagrant up

```

## Docker Configuration( docker-compose.yml )

```

services:
    frontend:
      build: ./client
      container_name: clientapp
      ports:
        - 3000:3000
      networks:
        - network-net
      depends on:
        - backend

    backend:
      build: ./backend
      container_name: backend
      ports:
        - 5000:5000
      networks:
        - network-net
      depends on:
        - mongo


    mongo:
      container_name: mongo_container
      image: mongo:latest
      restart: always
      volumes:
        - ./data:/data/db
      ports:
        - 27017:27017
      networks:
        - network-net

    networks:
      network-net:
      driver: bridge

  

      
        
```

## 