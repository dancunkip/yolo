## Docker Configration
The document entails  images, Dockerfile directives, networking, volume usag
### Ansible playgroup


### 1. Choice of the base image on which to build each container.
Chose the official node/alpine image because of the smaller size 


## Vagrant configuration
#### it will will be configured Using Ansible to Provision Vagrant for Docker 


##  Vagrant file
Add a vagrant file and add the ports requiredfor and initialize roles using the below command
```
      ansible-galaxy init <roleName>
```

And now you can run the playbook with ```
vagrantu up
```

