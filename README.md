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
| :-------------------------------------- | :---------------------------------------------------------- | --- |
| An isolated environment to run hardware | A virtual machine is an abstraction of a real world machine |
| Lightweight i.e. Don't need a full OS   | Heavy                                                       |
| All containers share the OS of the host |                                                             |
| Starts quickly                          |                                                             |     |

### Steps

1. Tell docker to bring up your application and Docker will automatically download and run the dependencies required in an isolated environment called a container using `docker-compose up`.
2.

### Resources

- [Docker with Mosh](https://www.youtube.com/watch?v=pTFZFxd4hOI)
