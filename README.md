# Understanding the basics of Docker
A very simple Node.js project to understand the basic concept of Docker and how it works.

# Build

Create Dockerfile in the root directory and add configurations in it. And build a Docker Image by the following command:

```docker build .```

Docker Image can also be built with a tag via:

```docker build -t {name} .```

# Run
To run a container, the following command can be used:

* ```docker run {container-tag || container-id}```

But it will be impossible to see what is expected since the browser runs on the local environment, yet the Docker container is a separate environment.

To check the app works properly, It needs to map the local port to the container's port.

It can be done by using the command:

* ```docker run -p {local-port}:{docker-port} {container-tag || container-id}```

# See the content of the container

The contents of the docker can be checked with the following command:

* ```docker exec -it {container-id} sh```

# On content change

Containers do not notice the changes of local files automatically. It will require rebuild.

To minimise the cache busting during the rebuild, make Dockerfile looks at package.json file first by:

```COPY ./package.json ./```