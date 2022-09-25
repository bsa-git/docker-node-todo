# DOCKER-NODE-TODO

A simple **to-do list** application built with [Nodejs](https://nodejs.org/en/). Used as an example to show basic operations with [Docker](https://docs.docker.com/) technology.

Main features of the application:

* [Expressjs](https://expressjs.com/) is used on the server side of the application.
* **Expressjs** is a minimal and flexible **Node.js** web application framework that provides a robust set of features for web application.
* Databases are used to store data. Uses a database type **SqlLite** or **My SQL**.
* For client side use a JavaScript library [React](https://reactjs.org/) for building user interfaces.

The main operations of the Docker technology are described in this application:

* Build the local container image (`docker build -t node-todo .`).
* Start the local container (`docker run -dp 3000:3000 node-todo`).
* Create a [Docker ID](https://hub.docker.com/signup) for free if you don’t have one.
* Sign in to [Docker Hub](https://hub.docker.com/). Enter **username** or **email** and passport.
* Create a **repo** on **Docker Hub**.
* Use the **docker tag** command to give the **node-todo** image a new name (`docker tag node-todo YOUR-USER-NAME/node-todo`).
* Share local **Docker image** on **Docker Hub**.
* Running the **push command** (`docker push YOUR-USER-NAME/node-todo`).
* Running our Image on a New Instance, [Play with Docker](https://labs.play-with-docker.com/).


## [Leane more...](http://bsa-git.github.io/docker-node-todo)