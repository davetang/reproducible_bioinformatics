## Reproducible bioinformatics

Workshop details for [BioC Asia 2019](https://bioconductor.github.io/BiocAsia/).

* Title: Reproducible bioinformatics
* Presenter: Dave Tang
* Key words: Docker; Conda; Bioconda; RStudio Server; Reproducibility; Project management
* Description: This workshop will discuss guidelines for ensuring reproducibility in bioinformatic data analysis and demonstrate how we can adhere to these guidelines through the use of various computational tools. You will be introduced to Conda and Docker and shown how they can be used to simplify the deployment of bioinformatics tools and create isolated software environments ensuring that analyses can be reproduced. The workshop will also discuss approaches for organising computational projects using the workflowr R package. By the end of the workshop, you will have learned some ideas behind carrying out reproducible research and can better communicate and share your work in a reproducible manner.
* Requirements: You will need to bring your own laptop. Please make sure that Docker is installed; see Setup information below. Some command line experience will be helpful but not required.
* Relevance: One of the most important aspects of scientific research is that someone else can reproduce your work. Even if a complex bioinformatics analysis is thoroughly described in the supplementary material of a paper and all raw data is provided, this doesn't guarantee that another other researchers can reproduce your work. This workshop is relevant to anyone who is interested in learning how to work in a manner that promotes reproducibility. In most cases, the person trying to reproduce your work is your future self. If you have looked back on your previous analyses and had trouble figuring out what you had done, this workshop is for you.

## Setup

If you are using Windows or macOS please install Docker Desktop from https://docs.docker.com/install/#supported-platforms. Docker Desktop for Windows requires Microsoft Windows 10 Professional or Enterprise 64-bit; for previous versions get Docker Toolbox. You can download Docker Desktop for Windows on [dockerhub](https://hub.docker.com/editions/community/docker-ce-desktop-windows/).

If you are using Linux please install Docker Engine - Community for your distro:

* CentOS - https://docs.docker.com/install/linux/docker-ce/centos/
* Debian - https://docs.docker.com/install/linux/docker-ce/debian/
* Fedora - https://docs.docker.com/install/linux/docker-ce/fedora/
* Ubuntu - https://docs.docker.com/install/linux/docker-ce/ubuntu/

If you are not using any of these operating systems, you're on your own!

Once Docker is installed, check the version using the terminal for Linux or macOS and using the Windows PowerShell for Windows.

```bash
docker --version
Docker version 19.03.5, build 633a0ea
```

Run the `hello-world` example, which will pull the latest `hello-world` image (if you don't already have this image) and run it.

```bash
docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/
```

Finally pull these images.

```bash
docker pull continuumio/miniconda3
docker pull davetang/rstudio_biocasia
```

Run `davetang/rstudio_biocasia`.

```bash
docker run --rm \
           -p 8888:8787 \
           -e PASSWORD=password \
           davetang/rstudio_biocasia
```

Now open your web browser (e.g. Firefox, Chrome, etc.) and paste `localhost:8888` into the address bar. The username is `rstudio` and the password is `password`.

## Useful links

* If you have never used R Markdown before, check out these series of tutorial - https://rmarkdown.rstudio.com/lesson-1.html
* Coursera course on the concepts and tools behind reporting modern data analyses - https://www.coursera.org/learn/reproducible-research
* Report Writing for Data Science in R - https://leanpub.com/reportwriting
* Workflowr website - https://jdblischak.github.io/workflowr/
* A comprehensive tutorial on getting started with Docker - https://github.com/prakhar1989/docker-curriculum
* Execute Docker containers without root privileges - https://github.com/indigo-dc/udocker

