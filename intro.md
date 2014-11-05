slidenumbers: true

# Introduction to Docker

## Containerization is the new virtualization

![](/Users/james/Dropbox/src/intro-to-docker/images/logo.png)

James Turnbull
@kartar

---

# who

![](images/owl.jpg)

 - VP of Engineering at Kickstarter
 - Advisor at Docker
 - Open source chap
 - Funny accent

---

# Kickstarter live in Sweden

![](images/sweden.png)

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

# But this isn't new?!?

![](/Users/james/Dropbox/src/intro-to-docker/images/dino.jpg)

---

# So why should I care?

## Software delivery mechanism
## Portability
## A bit like a VM but ...

![](/Users/james/Dropbox/src/intro-to-docker/images/caring.jpg)

---

# ... not like a VM

1. Containers boot faster
2. Containers have less overhead
3. Containers bring native performance
4. Containers are Cloud & VM-compatible

![](images/Virtual-Boy-Controller.jpg)

---

# Devs care about their app<br /><br />
# Ops cares about the containers

![](images/Separatory_funnel_with_oil_and_colored_water.jpg)

---

## Why developers care...

- Clean, safe, hygienic and portable
- No worries about dependencies
- Encourage good architecture

![](images/devs.jpg)

---

## Why operations care...

- Make the lifecycle more efficient
- Eliminate inconsistencies
- Support segregation of duties

![](images/Missile_Defense_Integration_and_Operations_Center.jpg)

---

## What can I use Docker for?

- Docker for CI/CD
- Packaging and deploying applications
- Build your own PAAS
- Deploy applications at hyperscale!

![](images/Chopsticks_usage.png)

---

## Does this work with Puppet or Chef?

- Chef and Puppet are state management tools
- Less complex
- Docker images are version controlled and layered
- Smaller, self-contained and lightweight

![](images/chef.jpg)

---

## Technology Stack

- Runs on most Linux distros
- Boot2Docker for OSX and Windows
- **Windows in the works!**
- Uses Linux kernel features

![](images/Anaconda_Stack.jpg)

---

# Docker Basics

## Image & Dockerfile
## The Docker Hub
## Container

![](images/Basic_computing_language_for_Atari_8-bit_computers.jpg)

---

# Building Docker images

```go
			FROM       ubuntu
			MAINTAINER James Turnbull "james@example.com"

			RUN apt-get -qqy update
			RUN apt-get install -qqy apache2
			ADD index.html /var/www/

			ENV APACHE_RUN_USER www-data
			ENV APACHE_RUN_GROUP www-data
			ENV APACHE_LOG_DIR /var/log/apache2

			VOLUME [ "/var/log/apache2" ]
			EXPOSE 80

			ENTRYPOINT ["/usr/sbin/apache2"]
			CMD ["-D", "FOREGROUND"]
```

---

# Building the image

```bash
$ sudo docker build -t="jamtur01/0redev" .
```

---

# Sharing the image

```bash
$ sudo docker push jamtur01/0redev
```

---

# Running the container

```bash
$ sudo docker run --name mywebsite -ti -p 80:80 jamtur01/0redev
```

---

# But there's more!

![](images/steak.jpg)

---

# What if we could componentize . . .

![](images/Component_video_jack.jpg)

---

# SSH

![](images/ssh.jpg)

---

# Managing a container

```bash
$ sudo docker exec -ti mywebsite /bin/bash
```

---

# Scheduling and jobs

![](images/days.jpg)

---

# Logging

![](images/Logging_in_Finnish_Lapland.jpg)

---

# Logging container

```bash
$ sudo docker run --volumes-from mywebsite -ti ubuntu /bin/bash
```

---

# Creates a new architecture

![](images/Sydney_Opera_House_Sails_edit02_adj.JPG)

---

# A new architecture that ...

- Separates orthogonal concerns
- Don't rebuild your app to change services
- Have different policies in domains
- Ship lighter apps

![](images/orth.jpg)

---

# Questions?

![](images/Arvin,_Kern_County,_California._..._Head_of_rural_family_asking_questions_regarding_the_size_of_his_._._._-_NARA_-_521653.jpg)
