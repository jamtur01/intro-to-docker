slidenumbers: true

#  Orchestrating Docker

## Containerization is the new virtualization

![](/Users/james/Dropbox/src/intro-to-docker/images/logo.png)

James Turnbull
@kartar

---

# who

![](images/owl.jpg)

 - CTO at Kickstarter
 - Advisor at Docker
 - Open source chap
 - Funny accent

---

# The Docker Book

![inline](/Users/james/Dropbox/src/intro-to-docker/images/cover.png)

 [www.dockerbook.com](http://www.dockerbook.com)

---

# Who are you folks?

![](images/who.JPG)

---

# What's this all about?

![](images/polar.jpg)

---

# What is Docker?

![](images/ContainerImage.png)

---

# Container virtualization

![](/Users/james/Dropbox/src/intro-to-docker/images/containers.jpg)

---

# Build, ship, run

![](/Users/james/Dropbox/src/intro-to-docker/images/container.jpg)

---

# Build once

![](/Users/james/Dropbox/src/intro-to-docker/images/bridge.jpg)

---

# Run in many places

![](/Users/james/Dropbox/src/intro-to-docker/images/seawall1.jpg)

---

# Isolated
# Layered
# Standard
# Content agnostic

![](/Users/james/Dropbox/src/intro-to-docker/images/Isolated_danger.jpg)

---

# Docker Basics

## Image & Dockerfile
## Container
## The Docker Hub

![](images/Basic_computing_language_for_Atari_8-bit_computers.jpg)

---

# Orchestrating Docker

## Compose
## Machine
## Swarm
## Kubenates and friends

---

![](images/dawson-cryings.jpg)

# Docker Compose

## Because it's not simple to build a stack

---

![](images/fig.jpg)

# Docker Compose

- Fast, isolated development environments using Docker.
- Quick and easy to start.
- Manages a collection of containers.

---

# Installing Compose

```bash
$ sudo pip install -U docker-compose
$ docker-compose --version
```

---

![](images/newton.jpg)

# Compose basics

- Build your apps with `Dockerfile`'s.
- Combine applications and images with a `docker-compose.yml` file.

---

# The Dockerfile

```json
FROM ubuntu:14.04
RUN apt-get -yqq update
RUN apt-get -yqq install nodejs npm
RUN ln -s /usr/bin/nodejs /usr/bin/node
RUN mkdir -p /var/log/nodeapp
ADD nodeapp /opt/nodeapp/
WORKDIR /opt/nodeapp
RUN npm install
```

---

# The docker-compose.yml file

```json
db:
  image: redis
  ports:
    - "6379"
web:
  image: jamtur01/fluentdemo
  command: nodejs server.js
  ports:
    - "3000:3000"
  links:
    - db
```

---

# Compose details

- Can build images, use existing or pull images
- Can map ports, manage links and create volumes
- Still single host centric.

---

# Start Compose

```bash
$ sudo docker-compose up
Creating compose_db_1...
Creating compose_web_1...
. . .
```

---

![](images/figtree.jpg)

# Demo

---

![](images/figben.jpg)

# Compose benefits

- Build complex local stacks.
- Consistent and shareable.
- No more...

---

![inline](images/fine.jpg)

---

# Docker Machine

## Builds machine

---

# Machine benefits

- Automatically build Docker servers.
- Manage Docker servers.
- Target local and cloud nodes.

---

# Demo

---

# Docker Swarm

- Clustering for Docker
- Manage multiple Docker daemons

---

# Questions?

![](images/Arvin,_Kern_County,_California._..._Head_of_rural_family_asking_questions_regarding_the_size_of_his_._._._-_NARA_-_521653.jpg)
