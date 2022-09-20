# Sample application

For the rest of this tutorial, we will be working with a simple todo list manager that is running in Node.js. If you’re not familiar with Node.js, don’t worry. No real JavaScript experience is needed.

<img alt="todo-list-sample" src="https://docs.docker.com/get-started/images/todo-list-sample.png" style="width:50%;">

## Get the app

Before we can run the application, we need to get the application source code onto our machine. For real projects, you will typically clone the repo. But, for this tutorial, we have created a ZIP file containing the application.

1. Download the App contents from the [getting-started repository.](https://github.com/docker/getting-started/tree/master) You can either pull the entire project or [download it as a zip](https://github.com/docker/getting-started/archive/refs/heads/master.zip) and extract the app folder out to get started with.

2. Once extracted, use your favorite code editor to open the project. If you’re in need of an editor, you can use [Visual Studio Code](https://code.visualstudio.com/). You should see the `package.json` and two subdirectories (`src` and `spec`).

<img alt="todo-list-sample" src="https://docs.docker.com/get-started/images/ide-screenshot.png" style="width:650px;margin-top:20px;">


## Build the app’s container image

In order to build the application, we need to use a Dockerfile. A Dockerfile is simply a text-based script of instructions that is used to create a container image. If you’ve created Dockerfiles before, you might see a few flaws in the Dockerfile below. But, don’t worry. We’ll go over them.

1. Create a file named `Dockerfile` in the same folder as the file `package.json` with the following contents.

```bash
FROM node:12-alpine
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```
2. If you haven’t already done so, open a terminal and go to the `app` directory with the `Dockerfile`. Now build the container image using the docker build command.

```bash
docker build -t node-todo .
```

## Start an app container

Now that we have an image, let’s run the application. To do so, we will use the `docker run` command (remember that from earlier?).

1. Start your container using the `docker run` command and specify the name of the image we just created:

```bash
docker run -dp 3000:3000 node-todo
```
> Remember the `-d` and `-p` flags? We’re running the new container in `detached` mode (in the background) 
> and creating a mapping between the host’s `port 3000` to the container’s `port 3000`. 
> Without the port mapping, we wouldn’t be able to access the application.


2. Once it has started, you can open your browser to [http://localhost:3000](http://localhost:3000).

## Recap

In this short section, we learned the very basics about building a container image and created a Dockerfile to do so. Once we built an image, we started the container and saw the running app.

Next, we’re going to make a modification to our app and learn how to update our running application with a new image. Along the way, we’ll learn a few other useful commands.