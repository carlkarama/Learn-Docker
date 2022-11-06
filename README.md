# Learn-Docker

A series of projects to consolidate my understanding of Docker

# What is Docker?

### Summary

---

An platform for building, running and shipping containers in a consistent manner. So that if your program works on your development machine, it can run and function the same way on other machines.

If you've been developing software for a while, you've probably run into this situation whereby your software works on your machine but doesn't somewhere else. This could be for a couple of reasons highlighted below.

- One or more files are missing i.e. Files not included in your deployment
- Software version mismatch i.e The target machine is running a different version of a software
- Different configuration settings i.e Environment variables are different across machines.

Docker allows you to handle these highlighted problems above by easily packaging your application and run it anywhere that runs Docker.

### Pros

- New developers don't have to spend soo much time configuring your application
- This isolated environment i.e containers, allows multiple applications use different versions of software to side by side.
- Developers can get rid of dependencies effortlessly because each application runs in its own separate environment. To ellaborate more, without Docker, as we work on more projects our development machine gets cluttered with soo many libraries and tools that are used by different applications. This can confuse the developer deciding whether to remove the libaries in fear it may break other projects. You can use this command `docker-compose down --rmi all`

## Containers vs Virtual Machine

| Container                               | Virtual Machine                                             |
| :-------------------------------------- | :---------------------------------------------------------- |
| An isolated environment to run hardware | A virtual machine is an abstraction of a real world machine |
| Lightweight i.e. Don't need a full OS   | Heavy                                                       |
| All containers share the OS of the host | Runs on virtual environments of the hardware                |
| Starts quickly                          | Starts slow                                                 |

### Steps

1. Begin by downloading the docker desktop app
2. Create a docker file with no extension
3. Tell docker which base image to run app on
4. Tell docker to package up our application `docker build -t <tagname> <directory where docker can find docker file>` e.g docker build -t hello-world .

### Syntax Example

``
//
//we start from a base image published on Docker Hub i.e node is built on top of a linux image & alpine is the
//distribution flavour of linux.
FROM node:alpine

//We need to copy all our program files from the source which in our case is the current directory e.g. (.) into ///the destination directory (/app) which is the image's filesystem.
//
COPY . /app

//
WORKDIR /app

// Use the command (CMD) to execute the app. Since the file we want to execute is in the /app directory
// we have to prefix it with a directory name e.g. (/app/app.js). Since this is a longer way of doing it
// we can use the above command to assume we are already within /app directory
CMD node app.js

### Resources

- [Docker with Mosh](https://www.youtube.com/watch?v=pTFZFxd4hOI)
