## Docker
[Home](../README.md) 

[Reference](https://wsvincent.com/beginners-guide-to-docker/)  
[Video](https://diveintodocker.com/ref-dfp)  


The important takeaways from this tutorial are this:

* Docker is a way to run Linux containers
Containers are a lightweight alternative to Virtual Machines  
* Dockerfile is a list of instructions for creating an image  
* Images are made up of one or more layers  
* Containers are a running instance of an image
docker-compose.yml controls how to run the container  
* Containers are stateless and ephemeral in nature. We can link the local filesystem via volumes but things become more complex with databases (which we didn’t cover here).  