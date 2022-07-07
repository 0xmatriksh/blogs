---
layout: post
title: "Docker and Containerization"
date: 2022-06-16 8:05:22 +0545
tags: [docker, devops]
excerpt: "This blog is about how we can implement containeraization with Docker"
thumbnail: "/assets/img/posts/docker.png"
# categories: jekyll update
---

![alt text]({{ '/assets/img/posts/docker.png' | relative_url}}){: .center-image }

Docker is one of the hot topics in today's world among developers and teams. It has made significant change in the way we develop the softwares.
Now, docker is one of the demanded skills to have as a developer. It is often desired as must have knowledge for different developer position role.

Docker was started in 2013 and right from the beginning it started to gain the hype and it grew with time.
The containerization concept in docker was loved by almost every developers. It basically means to contain all the essential code,
modules, libraries, system tools and settings in a single place. It is a standalone package of software which can be used to run the application in any environment we want.

### Why Containerization?

Since we understood the basic idea of containers, let’s understand why containerization. Before containerization, we should understand the concept called _virtualization_. It is basically an approach to host multiple applications in a single computer system. Have you ever heard of Virtual OS?
If not, no need to worry we will clearly understand within the next few lines. Virtual OS is the guest operating system on the top of our
host OS. For example: If we have Windows OS as operation system software in your machine, you can also have guest OS as Linux or even MacOS. This is possible because of Hypervisor. It is the firmware or software that enables multiple OS to run side by side.

So what is virtualization then?

Virualization is the concept of running multiple applications from different OS, which without the concept of virtualization, we could run only one. Also different big giants like Amazon, Microsoft are giving virtual machine through cloud computing and are very popular by using the same concept. A single hardware resources is shared to provide different virual operating system with certain hardware resource allocated to it. This has been and being used as one the most popular technique to host our applications and program. So AWS and Azure are very popular.

Okay, virtualization is good. Then why containerization?

Although, virtualization covers some problems but it has some flaws too. It is because of its architecture. Basically virtualization has running applications in multiple OSes which need to be installed. So having multiple OS in the same machine makes it slow and decreases performance. And also it had a portability issue. So this was to be solved. Then comes the lightweight and portable concept of containerization. Docker is one of the tools using the concept of containerization.

### what exactly is Docker?

Docker is the way of containerizing our application. It has some ups in comparison to Virtualization, as it should have. It does not require multiple OS like Virtualization, because of which it is very lightweight. The main idea of Docker Container, the package of your software, is to make it portable with all the essential components inside the same container. So that it can be easily run on any machine you want. Containers are great for continuous integration and continuous delivery (CI/CD) workflows. It has made the life of developers and devops teams a lot better.

The advantage docker provides is not only this much. Additionally, Docker lets us use the same OS kernel to host multiple applications. Therefore it can be flexible and can expand the resources the application needs when the other applications do not require those resources. This feature was not available in the Virtualization because of pre-partitioning the resource to each OS kernel.

With docker container, we can develop our application on modern architecture. While all the application are developed in past were monolithic, building monolithic apps in docker is not much beneficial as we are letting ourselves away from getting the benefit of staged deployment. Building the software with microservices is itself a great approach as it can allow us to maintain and develop different parts of the software separately. These independent components have their own container. And these containers can communicate with each other by a separate communication in a virtual network.

### How to use Docker

With docker we can easily create a container. We just require a Docker file and docker compose file to start. Docker file builds the docker image. It basically defines all the dependencies the application requires and meanwhile docker compose file helps to deploy, combine and configure multiple docker containers.

Another important aspect of Docker is Docker Hub. It is a public service which contains different pre-built containers which can be imported in other containers if needed. It has container images like the the image of Python which we can pull(download) if we need.

Docker basically maintains the environment for application. Developers do not need development tools in their machine to build and run the application. It is handled by the docker container itself, by installing docker. Then after we can clone the code, build and finally run the application from single code.

The most important part about docker is it can be used in all types of applications from monolithic codes to the microservices of modern day. There are lots of advantages to Docker. There are few books written on Docker too. You can definitely read them to learn more about Docker.

### Simple Docker Setup

#### Docker file for simple Flask application

```
# syntax=docker/dockerfile:1
FROM python:3.7-alpine
WORKDIR /code
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
RUN apk add --no-cache gcc musl-dev linux-headers
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
EXPOSE 5000
COPY . .
CMD ["flask", "run"]
```

#### Similarly, Docker compose yaml file with redis service

```
# docker-compose.yml
version: "3.9"
services:
  web:
    build: .
    ports:
      - "8000:5000"
  redis:
    image: "redis:alpine"
```

#### And to build the app with compose

```
docker-compose up
```

Hope you enjoy reading this.
I am open to suggestions or if there are some queries.

Thank you. My email : *kishmat17@gmail.com*

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]: https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
