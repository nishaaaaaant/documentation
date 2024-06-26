---
title: Docker - Install Engine
author: wale soyinka
contributors:
date: 2021-08-04
tags:
  - docker
---

# Introduction

The Docker Engine can be used running native Docker style container workloads on Rocky Linux servers. This is sometimes preferred to running the full Docker Desktop environment.

## Add the Docker repository

Use the `dnf` utility to add the Docker repository to your Rocky Linux server. Type:

```bash
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

## Install the needed packages

Install the latest version of Docker Engine, `containerd`, and Docker Compose, by running:

```bash
sudo dnf -y install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

## Start and enable Docker (`dockerd`)

Use `systemctl` to configure Docker to automatically startup upon reboot and simultaneously start it now. Type:

```bash
sudo systemctl --now enable docker
```

### Notes

```docker
docker-ce               : This package provides the underlying technology for building and running docker containers (dockerd) 
docker-ce-cli           : Provides the command line interface (CLI) client docker tool (docker)
containerd.io           : Provides the container runtime (runc)
docker-compose-plugin   : A plugin that provides the 'docker compose' subcommand 
```
