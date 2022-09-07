# loktionovam_microservices

loktionovam microservices repository

* [loktionovam_microservices](#loktionovam_microservices)
  * [Homework-12: Containerization technologies. Introduction to Docker](#homework-12-containerization-technologies-introduction-to-docker)
  * [Homework-13: Docker containers. Docker under the hood](#homework-13-docker-containers-docker-under-the-hood)
    * [13.1 What was done](#131-what-was-done)
    * [13.2 How-to start the project](#132-how-to-start-the-project)
    * [13.2.1 Docker and docker machine cheat sheet. Building otus-reddit image](#1321-docker-and-docker-machine-cheat-sheet-building-otus-reddit-image)
    * [13.2.2 Set up infra. Prerequisites - creating the ssh keys and a GCP service account](#1322-set-up-infra-prerequisites---creating-the-ssh-keys-and-a-gcp-service-account)
    * [13.2.2 Set up infra. Building docker-host-base image by packer](#1322-set-up-infra-building-docker-host-base-image-by-packer)
    * [13.2.3 Set up infra. Creating the docker host instances via Terraform](#1323-set-up-infra-creating-the-docker-host-instances-via-terraform)
    * [13.2.2 Set up infra. Start the reddit application](#1322-set-up-infra-start-the-reddit-application)
    * [13.3 How-to check the project](#133-how-to-check-the-project)
  * [Homework-14: Docker images. Microservices](#homework-14-docker-images-microservices)
    * [14.1 What was done](#141-what-was-done)
    * [14.2 How-to start the project](#142-how-to-start-the-project)
    * [14.3 How-to check the project](#143-how-to-check-the-project)
  * [Homework-15: Docker networks, docker-compose](#homework-15-docker-networks-docker-compose)
    * [15.1 What was done](#151-what-was-done)
    * [15.2 How-to start the project](#152-how-to-start-the-project)
    * [15.3 How-to check the project](#153-how-to-check-the-project)
  * [Homework-16: Gitlab CI. Continuous integration process](#homework-16-gitlab-ci-continuous-integration-process)
    * [16.1 What was done](#161-what-was-done)
    * [16.2 How-to start the project](#162-how-to-start-the-project)
    * [16.3 How-to check the project](#163-how-to-check-the-project)
  * [Homework-17: Gitlab CI. Continuous delivery](#homework-17-gitlab-ci-continuous-delivery)
    * [17.1 What was done](#171-what-was-done)
    * [17.2 How-to start the project](#172-how-to-start-the-project)
    * [17.3 How-to check the project](#173-how-to-check-the-project)
  * [Homework-18: Introduction to a monitoring. Monitoring systems](#homework-18-introduction-to-a-monitoring-monitoring-systems)
    * [18.1 What was done](#181-what-was-done)
    * [18.2 How-to start the project](#182-how-to-start-the-project)
    * [18.3 How-to check the project](#183-how-to-check-the-project)
  * [Homework-19: Monitoring of the application and the infrastructure](#homework-19-monitoring-of-the-application-and-the-infrastructure)
    * [19.1 What was done](#191-what-was-done)
    * [19.2 How-to start the project](#192-how-to-start-the-project)
    * [19.3 How-to check the project](#193-how-to-check-the-project)
  * [Homework-20: Logging and distributed tracing](#homework-20-logging-and-distributed-tracing)
    * [20.1 What was done](#201-what-was-done)
      * [Resolving the problem of posts slow loading](#resolving-the-problem-of-posts-slow-loading)
    * [20.2 How-to start the project](#202-how-to-start-the-project)
    * [20.3 How-to check the project](#203-how-to-check-the-project)
  * [Homework-21: Introduction to Kubernetes](#homework-21-introduction-to-kubernetes)
    * [21.1 What was done](#211-what-was-done)
    * [21.2 How-to start the project](#212-how-to-start-the-project)
    * [21.3 How-to check the project](#213-how-to-check-the-project)
  * [Homework-22: Kubernetes. Deploying a cluster and applications. Security model](#homework-22-kubernetes-deploying-a-cluster-and-applications-security-model)
    * [22.1 What was done](#221-what-was-done)
    * [22.2 How-to start the project](#222-how-to-start-the-project)
  * [Homework-23: Kubernetes. Networks, Storages](#homework-23-kubernetes-networks-storages)
    * [23.1 What was done](#231-what-was-done)
    * [23.2 How-to start the project](#232-how-to-start-the-project)
    * [23.3 How-to check the projects](#233-how-to-check-the-projects)
  * [Homework-24: CI/CD in Kubernetes](#homework-24-cicd-in-kubernetes)
    * [24.1 What was done](#241-what-was-done)
    * [24.2 How-to check the project](#242-how-to-check-the-project)
    * [24.3 How-to check the project](#243-how-to-check-the-project)
  * [Homework-25: Kubernetes. Monitoring and logging](#homework-25-kubernetes-monitoring-and-logging)
    * [25.1 What was done](#251-what-was-done)
    * [25.2 How-to start the project](#252-how-to-start-the-project)
    * [25.3 How-to check the project](#253-how-to-check-the-project)

## Homework-12: Containerization technologies. Introduction to Docker

Main tasks:

* Installing docker

* Basic working with docker cli - creating, starting, stopping, removing containers, building images from containers, removing images

Advanced task *: describe the difference between a container and an image

About images.

* Docker image consists of read-only layers, i.e.

```json
            "Layers": [
                "sha256:711e4cb62f50eb37292a0df824072b6a818211e3f9b3aae75a2067e65fa32eca",
                "sha256:a0e188d0e2789aeb82bd848958f432fbc19704bfa3337e0cad00545b43550f51",
                "sha256:6eaddaf493f101a62bb0875185e706424a33636db5d8a55945d63f6f870d7dd2",
                "sha256:07b9c3c04cbdf53317cb326fe3db42073366add5a8919f590e1574252ac6f8c9",
                "sha256:709bdd00b1a496a5ee836b8bc3e0f371fa114e9ff4cc524c0862696bbfc69c9c",
                "sha256:11266888239dc2bbd77759fb2c8df2eb2284983f817c745605d42d46402258a9"
     ]
```

* Each layer is a diff from previous one.

* Different images use the common layers (do not need to download every layer if you already have it).

* There is a description of containers which started from an image

```json

        "Container": "b8fc5d0067d0ebc04a61b579250dc1753597e75fcc7554b2bebb6aefeb7abcp "${REPO_PATH}"/",
        "ContainerConfig": {
            "Hostname": "b8fc5d0067d0",
```

About containers.

* Creation of a new container creates a COW read/write layer upon an image, this layer named as a container layer. This is a difference between containers and images (when you remove a containers then the R/W layer is removed too but an underlayer image still exist)

* While the writing the file to container it looks  the layers  (from top to bottom, from the newest to the oldest). The file is copied to a writable layer and the operations of writing take place in this copied file and the container doesn't have access to these underlying read-only copies of this file.

* There is a state of container related to its runtime (pid, hardware resources - a memory, a cpu, network interfaces), i.e.

```json
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
...
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
```

So containers are about runtime+r/w image and images are about storing and delivery of applications.

## Homework-13: Docker containers. Docker under the hood

### 13.1 What was done

Main tasks:

* docker host was created in GCP via a docker machine

* docker image  otus-reddit:1.0 was built

* the docker hub repository was created and the otus-reddit:1.0 image was uploaded

Advanced tasks *:

* Added an ansible configuration to docker-monolith/infra/ansible to set up a docker host (role: docker_host) and set up a dynamic inventory via gce.py

* Added a configuration to docker-monolith/infra/packer to create an image with installed docker

* Added a configuration to docker-monolith/infra/terraform to up and running instances docker-host-xxx the number of them is set up in the count variable

### 13.2 How-to start the project

### 13.2.1 Docker and docker machine cheat sheet. Building otus-reddit image

```bash
docker-machine create --driver google  --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts  --google-machine-type n1-standard-1   --google-zone europe-west1-b  docker-host

docker-machine ls

docker-machine env docker-host
export DOCKER_TLS_VERIFY="1"
export DOCKER_HOST="tcp://ip:port"
export DOCKER_CERT_PATH="/some/path/to/.docker/machine/machines/docker-host"
export DOCKER_MACHINE_NAME="docker-host"
# Run this command to configure your shell:
# eval $(docker-machine env docker-host)

eval $(docker-machine env docker-host)

# start htop (PID from the container namespaces)
docker run --rm -ti tehbilly/htop

# start htop (PID из host namspaces)
docker run --rm --pid host -ti tehbilly/htop

docker run --help | grep "\-\-pid "
      --pid string                     PID namespace to use


# -t - tag (--tag=)
docker build -t reddit:latest .

# -d background mode (--detach=true)
# --network - use host network
docker run --name reddit -d --network=host reddit:latest

# create a tag alias to reddit:latest
docker tag reddit:latest loktionovam/otus-reddit:1.0
# push the docker image to the docker registy
docker login
docker push loktionovam/otus-reddit:1.0

# start the existing container
docker stop reddit
docker start reddit

# logs
docker logs reddit -f

# start bash
docker exec -it reddit bash

# remove the container
docker rm reddit

# starting the container without starting the application
docker run --name reddit --rm  -it loktionovam/otus-reddit:1.0 bash
root@96aba478ca67:/# ps ax | grep start
   16 pts/0    S+     0:00 grep --color=auto start

# the full information about the image
docker inspect loktionovam/otus-reddit:1.0 

docker inspect loktionovam/otus-reddit:1.0 -f '{{.ContainerConfig.Cmd}}'
[/bin/sh -c #(nop)  CMD ["/start.sh"]]

# show the changed files and directories in the container
docker diff reddit
```

### 13.2.2 Set up infra. Prerequisites - creating the ssh keys and a GCP service account

```bash
export REPO_PATH=$(pwd)
export GCP_PROJECT=docker-project-name-here
ssh-keygen -t rsa -f ~/.ssh/docker-user -C 'docker-user' -q -N ''

gcloud iam service-accounts create docker-user --display-name docker-user

gcloud projects add-iam-policy-binding "${GCP_PROJECT}" --member serviceAccount:docker-user@"${GCP_PROJECT}".iam.gserviceaccount.com --role roles/editor
```

### 13.2.2 Set up infra. Building docker-host-base image by packer

```bash
# Creating a docker host image with a preinstalled docker engine
cd "${REPO_PATH}"/docker-monolith/infra
packer build -var-file=packer/variables.json packer/docker_host.json
```

### 13.2.3 Set up infra. Creating the docker host instances via Terraform

```bash
cd "${REPO_PATH}"/docker-monolith/infra/terraform
# Before you execute the commands you need to set up terraform.tfvars to create a remote backend
terraform init
terraform apply

cd "${REPO_PATH}"/stage
# Before you execute the commands you need to configure terraform.tfvars to create the docker host instances and the firewall rules
terraform init
terrafrom apply
```

### 13.2.2 Set up infra. Start the reddit application

```bash
cd "${REPO_PATH}"/docker-monolith/infra/ansible
# Copy the service account secret file
gcloud iam service-accounts keys create environments/stage/gce-service-account.json --iam-account docker-user@"${GCP_PROJECT}".iam.gserviceaccount.com

# Configure gce dynamic inventory
ansible-playbook playbooks/gce_dynamic_inventory_setup.yml

# Deploy the reddit app to the instances that were created earlier by terraform
ansible-playbook playbooks/site.yml
```

### 13.3 How-to check the project

* Go to link <http://ip_address:9292> to access to the reddit application, execute this to show ip_address:

```bash
# get all ip addresses
cd "${REPO_PATH}"/docker-monolith/infra/terraform/stage
terraform output
```

## Homework-14: Docker images. Microservices

### 14.1 What was done

Main tasks:

* built docker images for comment, ui, post microservices
* created the reddit application docker network
* created the mongodb docker volume
* created the containers based on built images

Advanced tasks *:

* Changing the network aliases, usage of env variables

```bash
docker run -d --network=reddit --network-alias=post_db_alias --network-alias=comment_db_alias mongo:latest
docker run -d --network=reddit --network-alias=post_alias -e 'POST_DATABASE_HOST=post_db_alias' loktionovam/post:1.0
docker run -d --network=reddit --network-alias=comment_alias -e 'COMMENT_DATABASE_HOST=comment_db_alias' loktionovam/comment:1.0
docker run -d --network=reddit --network-alias=ui_alias -e 'POST_SERVICE_HOST=post_alias' -e 'COMMENT_SERVICE_HOST=comment_alias' loktionovam/ui:1.0
```

Advanced tasks *:

* Reduce the image size of comment, ui, post

```bash
# docker ui image size
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
loktionovam/ui      3.2                 b92f70287088        11 seconds ago      34.5MB # alpine, multi-stage build, cache cleaning
loktionovam/ui      3.1                 8e94d1738f8f        4 minutes ago       37.5MB # alpine, multi-stage build
loktionovam/ui      3.0                 0054caafcade        14 minutes ago      210MB # alpine
loktionovam/ui      2.0                 5f494c53de90        23 minutes ago      460MB # ubuntu 16.04
loktionovam/ui      1.0                 1dc4afe3d94c        26 minutes ago      777MB # ruby 2.2
```

```bash
# docker post image size
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
loktionovam/post    2.2                 e13a2539eef3        6 minutes ago       35.1MB # alpine:3.8, multi-stage build, venv packages cleaning, pyc files removing
loktionovam/post    2.1                 a4978e47831e        13 minutes ago      57.5MB # alpine:3.8, multi-stage build, venv packages cleaning
loktionovam/post    2.0                 324095723244        21 minutes ago      62.6MB # alpine:3.8, multi-stage build
loktionovam/post    1.0                 228a932d5c0d        3 hours ago         102MB # python:3.6.0-alpine
```

```bash
# docker comment image size
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
loktionovam/comment   2.0                 d42d889bed54        18 seconds ago      30.1MB # alpine, multi-stage build, cache cleaning
loktionovam/comment   1.0                 d1e034889328        4 hours ago         769MB # ruby 2.2
```

### 14.2 How-to start the project

* we assume that there is the  **docker-host** and it has address  **docker_host_ip**

```bash
docker-machine ls
NAME          ACTIVE   DRIVER   STATE     URL                       SWARM   DOCKER        ERRORS
docker-host   *        google   Running   tcp://docker_host_ip:2376           v18.06.0-ce

eval $(docker-machine env docker-host)
```

* To build docker images for comment, post and ui microservices

```bash
cd src
docker build -t loktionovam/comment:2.0  ./comment
docker build -t loktionovam/post:2.2  ./post-py
docker build -t loktionovam/ui:3.2  ./ui
```

* To start the project

```bash
docker network create reddit
docker volume create reddit_db

docker run -d --network=reddit --network-alias=post_db \
 --network-alias=comment_db -v reddit_db:/data/db mongo:latest

docker run -d --network=reddit --network-alias=post loktionovam/post:2.2

docker run -d --network=reddit --network-alias=comment loktionovam/comment:2.0

docker run -d --network=reddit -p 9292:9292 loktionovam/ui:3.2
```

### 14.3 How-to check the project

To check the project go to <http://docker_host_ip:9292> and you will be able to create a post and add a comment

## Homework-15: Docker networks, docker-compose

Main tasks:

* Working with none, host, bridge docker networks
* Install docker-compose
* Build reddit application images via docker-compose
* Launch the reddit application via docker-compose
* Change a prefix in docker-compose

In docker-compose the names of prefixes of containers are set up by env variable **COMPOSE_PROJECT_NAME** that by default is equal to a project directory name:

```bash
cd /some/path/to/project_directory
basename $(pwd)
```

You can redefine this variable in **.env**:

```bash
# Defaul setting COMPOSE_PROJECT_NAME to the basename
# Change this value to setup containers prefix name
# COMPOSE_PROJECT_NAME=
```

Advanced tasks *:

* Create docker-compose.override.yml that allows to change application code without a rebuilding of docker images and to launch ruby applications in a debug mode with two workers.

### 15.1 What was done

* Created a container with none network driver, tested its network interfaces configuration

* Created a container with host network driver, tested its network interfaces configuration

* Created a container with bridge network driver, applied the network aliases

* Created docker networks: front_net (for ui, post, comment containers) and back_net (for mongo, post, comment containers)

* Checked out a linux network stack (net namespaces, iptables)

* Installed docker-compose, docker-compose.yml was written

* Developed .env to set up docker-compose via environment variables (image versions, a project prefix and so on)

* Developed docker-compose.override.yml that allows to change application code without a rebuilding of docker images and to launch ruby applications in a debug mode.

### 15.2 How-to start the project

* We assume that there is  **docker-host** and it has an address **docker_host_ip** and also **docker-compose** is installed:

```bash
docker-machine ls
NAME          ACTIVE   DRIVER   STATE     URL                       SWARM   DOCKER        ERRORS
docker-host   *        google   Running   tcp://docker_host_ip:2376           v18.06.0-ce

eval $(docker-machine env docker-host)
```

```bash
cd src
docker-compose up -d
```

### 15.3 How-to check the project

Go to the link <http://docker_host_ip:9292> to access to reddit application.

## Homework-16: Gitlab CI. Continuous integration process

Main tasks: install Gitlab CI, create a code repository, describe continuous integration stages

Advanced tasks *: automate a deployment and a registering a gitlab runner, integrate a gitlab pipeline with slack

### 16.1 What was done

* Added boot disk size parameter to the docker_host terraform module, added a firewall configuration to the docker host in terraform

* Added a docker compose support to the docker_host ansible role

* Rebuilt packer image to support docker compose docker-host-base

* Added gitlab_omnibus ansible role to auto deploy gitlab server, developed the role tests (molecula and testinfra), added a healthchek to docker compose configuration

* Added gitlab_omnibus.yml playbook to deploy a gitlab instance to GCP

* Added a gitlab pipeline

* Added gitlab_runner ansible role to auto deploy gitlab runner, developed the role tests (molecula and testinfra)

* Added gitlab_runner.yml playbook to auto deploy and registering a gitlab runner

* Added the reddit application and tests, added the tests running to a gitlab CI/CD

* Added slack integration <https://devops-team-otus.slack.com/messages/CB4BAETU5/>

### 16.2 How-to start the project

We assume that there is a terraform configuration that is described here **Homework-13**

* Build a new docker-host-base with supporting of a docker compose via packer

```bash
cd infra
packer build -var-file=packer/variables.json packer/docker_host.json
```

* Set up a boot size in terraform and redeploy the docker host

```bash
cd infra/terraform/stage
# настроить size = 50 в terraform.tfvars
# и пересоздать docker host
terraform taint -module=docker_host google_compute_instance.docker_host
terraform apply -auto-approve
terraform output
```

* Install a gitlab server

```bash
cd gitlab-ci/ansible
ansible-playbook playbooks/gitlab_omnibus.yml
```

* Configure a user, a project and ao on in the gitlab server

* Install and register a gitlab runner. Set up the `gitlab_runner_token` и `gitlab_runner_coordinator_url` variables in `~/.ansible/gilab_runner_credentials.yml` and execute the playbook:

```bash
cd gitlab-ci/ansible
ansible-playbook playbooks/gitlab_runner.yml
```

### 16.3 How-to check the project

After configuration of the CI/CD in the gitlab, you can push the changes and check the pipeline status out (**passed**)

```bash
git remote add gitlab http://<your-vm-ip>/homework/example.git
git push gitlab gitlab-ci-1
```

## Homework-17: Gitlab CI. Continuous delivery

Main tasks: improve the existing pipeline and add the environments to it

Advanced tasks *: a new server should be automatically created for environment after pushing a new branch. There also should be ability to remove this server by clicking on a button in a gitlab interface

Advanced tasks **: add building of the docker images of the reddit application and the built images should be deployed to the server which was created for this branch

### 17.1 What was done

* Added **staging, production** steps to the pipeline

* Added **reddit_monolith** ansible role to deploy container to a docker host

* Changed **reddit_app.yml** playbook in consideration of **reddit_monolith**

* Developed reddit application Dockerfile

* Developed Dockerfile that contains the infrastructure utilities like terraform and ansible

* Added the resources to provisioning the application to docker_host module (terraform)

* Building and pushing the reddit, app_provision docker images added to the build step

* Added **branch_start_review** step to CD to auto deploy the servers per branch and deploy the reddit application to them. For each branch a new instance of a docker host is created by the terraform workspace and the reddit application is deployed by reddit_app.yml playbook to it

* Added **branch_stop_review** to CD to remove the servers

### 17.2 How-to start the project

We assume that a gitlab server is already configured and a gitlab runner is registered on it

Add these variables to CI/CD:

* `CI_GOOGLE_CREDENTIALS` - credentials to connect to GCP via terraform

* `DOCKER_REGISTRY_USER` - docker hub registry user

* `DOCKER_REGISTRY_PASSWORD` - docker hub registry password

* `GCE_SERVICE_ACCOUNT` - content of a GCP service account credentials file. Used to set up a dynamic inventory via gce.py (gce_py ansible role)

* `GCP_PROJECT` - GCP project name

* `SSH_PRIVATE_KEY`, `SSH_PUBLIC_KEY` - ssh key pair to connect to a docker host

After a pushing a new branch to a gitlab server a new environment will be created and the reddit application will be deployed on it.

### 17.3 How-to check the project

After **branch_start_review** step completed successfully go to the link <http://docker_host_external_ip:9292> to connect to a newly deployed application

```bash

Outputs:

docker_host_external_ip = [
    35.240.19.232
]
Job succeeded
```

After the application review delete it by pressing **branch_stop_review**

## Homework-18: Introduction to a monitoring. Monitoring systems

Main task: install and configure a Prometheus; microservices monitoring; host metrics collection by a exporter

Advanced task *: add mongodb monitoring to Prometheus, pin the exporter version to the latest stable

Advanced task *: add comment, post, ui monitoring to Prometheus via blackbox exporter, pin the exporter version to the latest stable

Advanced task*: develop a Makefile to build and push docker images

### 18.1 What was done

* The project structure refactoring, added docker and monitoring directories

* Added a prometheus service to the docker compose

* Added node-exporter to the prometheus and docker compose

* Developed Dockerfile to build a mongodb prometheus exporter by percona (the docker image built upon scratch), added a mongodb monitoring to prometheus and docker compose

* Developed Dockerfile to build a blackbox exporter; added  ui (blackbox-http), post (blackbox-tcp), comment (blackbox-tcp) monitoring

* Developed the Makefile to build and push docker images; starting and stopping microservices by the Makefile

### 18.2 How-to start the project

* We assume that the **docker, docker compose** are already installed

* Install make

```bash
apt-get update && apt-get install make
```

* To build and run containers

```bash
make up
```

* To build and push docker images

```bash
make all
```

* To stop and remove running containers

```bash
make down
```

* To build the docker image (ui)

```bash
make ui_build
```

* To push the docker image (ui)

```bash
make ui_push
```

* To build and push image (ui)

```bash
make ui
```

### 18.3 How-to check the project

* Run in the root of the repository

```bash
make up
```

After the containers building and running go to the link <http://localhost:9292>

Go to the <http://localhost:9090> to access to prometheus interface

* To build and push all containers

```bash
make all
```

they will be here <https://hub.docker.com/r/loktionovam>

## Homework-19: Monitoring of the application and the infrastructure

### 19.1 What was done

Main task: docker containers monitoring; metrics visualization; the application metrics collection and collecting of business metrics; alerting

Advanced task *: added telegraf, grafana, stackdriver, autoheal targets to the Makefile

Advanced task *: added a docker host configuration to collect the metrics by a prometheus to docker-host ansible role, added grafana dashboard to visualize them (Docker_Engine_Metrics.json)

<https://grafana.com/dashboards/1229>

```bash
# Docker native metrics
curl http://172.17.0.1:9323/metrics 2>/dev/null| grep -E "^# " -v | wc -l
339
```

```bash
# Cadvisor metrics (their total count is depends on how many containers are running)
curl http://localhost:8080/metrics 2>/dev/null| grep -v "^# " | wc -l
3950

# the number of unique metrics in Cadvisor
total: 58
```

Advanced task *: added monitoring via telegraf, added a grafana dashboard `Docker_Performance_Monitoring.json` to visualize the metrics that are collected by the telegraf

```bash
# telegraf docker metrics
curl http://localhost:9273/metrics 2>/dev/null 2>/dev/null | grep -v "#"  metrics  | grep docker | wc -l
926
```

Advanced task *: added `UIHTTPHighResponceLatency` alert (95-й percentile of UI response time)

Advanced task *: configured integration between alertmanager and mailgun to delivery alert messages via email I couldn't find a good way to store the secret data in the alertmanager except to store them in the configuration file ([https://github.com/prometheus/alertmanager/issues/504]), so I added generating of this file in the runtime by `docker-entrypoint.sh` and the secret file `alertmanager.secrets` is located next to `Dockerfile` and configured via `configure_microservices.yml` ansible playbook while a host is created by terraform. The `alertmanager/config.yml` file is used only by the tests of this homework and used nothing else. To travis CI added support of `alertmanager.secrets` (the data is encrypted in `secrets.tar.enc`)

Advanced task **: added auto loading of grafana dashboards and datasources, refactored the dashboards `json` files to support autoloading (the root of the problem is described here [https://community.grafana.com/t/what-is-the-correct-way-to-save-dashboard-json-for-use-in-provisioning/5254/5])

Advanced task **: added monitoring via stackdriver prometheus exporter (the full list of metrics is here [https://cloud.google.com/monitoring/api/metrics_gcp]), added the `GCP stackdriver`  dashboard to a grafana. Stackdriver samples the metrics once per 60 seconds and you can access to them only after 240 seconds what can be problematic  for the prompt detection and elimination of problems (but it can not only collect the hosts metrics but many other GCP metrics too, for example storage or loadbalancing metrics)

```bash
# stackdriver metrics
curl http://localhost:9255/metrics 2>/dev/null | grep -E "^# " -v | wc -l
94
```

Advanced task **: added the INSERT_DB_LATENCY, UPDATE_DB_LATENCY, VOTE_COUNT metrics collection to the post application, added `Post_DB_stats.json` dashboard to grafana to display the db operation latencies, added the chart `Vote rate` to the Business_Logic_Monitoring dashboard

Super advanced task))) ***: trickster added to a microservices configuration, the grafana datasources was changed from prometheus to trickster, added a trickster metrics collection to the prometheus

Super advanced task ***: added autoheal+AWX to automatic healing of infrastructure. Added `awx_wrapper` ansible role that deploys AWX, creates an organization, a project, the necessary credentials, an inventory and a job template there to fix the problems with the microservices. Added building and running autoheal, added `autoheal` ansible role to autodeploy autoheal (autoheal is nailed to a kubernetes so the role uses a `minikube` to launch it, the problem discussion is here [https://github.com/openshift/autoheal/issues/110]). Added `mgmt_host.yml` ansible playbook to autodeploy AWX+autoheal. Added the `mgmt_host.json` packer template to bake an AWX+autoheal node image. Added the `mgmt_host` terraform module to autoprovisioning  AWX+autoheal on the dedicated GCE instance, this module added to the stage/prod terraform configuration.

### 19.2 How-to start the project

We assume that there is a mailgun account and the alertmanager configuration parameters

* Configure these files

```bash
find . -name "*.example"

./infra/packer/variables.json.example
./infra/terraform/stage/terraform.tfvars.example
./infra/terraform/terraform.tfvars.example
./infra/terraform/prod/terraform.tfvars.example
./monitoring/stackdriver/gce-service-account.json.example
./monitoring/alertmanager/alertmanager.secrets.example
```

* Install ansible roles dependencies

```bash
cd infra/ansible
ansible-galaxy install -r roles/awx_wrapper/requirements.yml
```

* Create the `docker_host`, `mgmt_host` images via packer

```bash
cd ..
packer build -var-file=packer/variables.json packer/mgmt_host.json
packer build -var-file=packer/variables.json packer/docker_host.json
```

* Create a stage environment

```bash
cd terraform
terraform init
terraform apply -auto-approve
cd stage
terraform init
terraform apply -auto-approve
```

### 19.3 How-to check the project

The two GCE instances would be created: `docker-host-default-001` (microservices), `mgmt-host-default-001` (AWX+autoheal)

```bash
docker_host_external_ip = [
    docker_host_ip
]
mgmt_host_external_ip = mgmt_host_ip
```

and on the `docker-host-default-001` these resources would be created:

```bash
http://docker_host_ip:9292 - reddit ui
http://docker_host_ip:3000 - grafana ui
http://docker_host_ip:9090 - prometheus ui
```

and `mgmt-host-default-001`

```bash
http://mgmt_host_ip  - AWX ui
```

For example if you kill the `ui` container you will receive an alert message in the slack and an email

```bash
[1] Firing
Labels
alertname = InstanceDown
instance = ui:9292
job = ui
severity = page
Annotations
description = ui:9292 of job ui has been down for more than 1 minute
summary = Instance ui:9292 down
```

and autoheal+AWX will restart the failed service by the `run_microservices` AWX job template, you can check the autoheal logs:

```bash
I1017 16:11:10.524400       1 alerts_worker.go:135] Checking rule 'start-services' for alert 'InstanceDown'
I1017 16:11:10.524507       1 alerts_worker.go:103] Rule 'start-services' matches alert 'InstanceDown'
I1017 16:11:10.524516       1 alerts_worker.go:174] Running rule 'start-services' for alert 'InstanceDown'
I1017 16:11:11.120843       1 awx_action_runner.go:117] Running AWX job from project 'otus' and template 'run_microservices' to heal alert 'InstanceDown'
I1017 16:11:11.740007       1 awx_action_runner.go:164] Request to launch AWX job from template 'run_microservices' has been sent, job identifier is '3'
I1017 16:15:38.765453       1 active_jobs_worker.go:27] Going over active jobs queue
I1017 16:15:39.180936       1 awx_action_runner.go:213] Job 3 status: successful
```

## Homework-20: Logging and distributed tracing

Main task: collect unstructured logs, visualize logs, collect structured logs

Advanced task *: add an additional filter to fluentd to parse the UI service logs

Advanced task*: configure a distributed tracing via zipkin; the problem solving via zipkin

### 20.1 What was done

* ui, post, comment microservices was updated to versions that support a centralized log collection and a distributed tracing

* Added a fluentd docker configuration

* Added a configuration (`docker-compose-logging.yml`) to logging via EFK stack

* Added the `up_logging`, `down_logging`, `run_logging` targets to the Makefile to simplify the building and running the logging services

* Enabled EFK logging for ui, post microservices

* (*) Developed two fluentd grok filters for the ui service unstructured logs

* (*) Configured distributed tracing by zipkin, resolved the problem of posts slow loading

* Added the kibana, zipkin firewall rules to the terraform

#### Resolving the problem of posts slow loading

* In the zipkin traces we can observe that the post loading is slow down (> 3 seconds) in the `post` microservice  (span `db_find_single_post`)

```json
{"traceId":"b75e6044b69e4b97","parentId":"10936eab56fcedd8","id":"7bf8af12a44a74dd","kind":"CLIENT","name":"db_find_single_post","timestamp":1539891825806233,"duration":3005865,"localEndpoint":{"serviceName":"post","ipv4":"172.27.0.5","port":5000}},
```

* Find `span=db_find_single_post` span in `post_app.py` and the problem is `time.sleep(3)`. You need to remove this sleep, rebuild and rerun the container

```python
@zipkin_span(service_name='post', span_name='db_find_single_post')
def find_post(id):
...
        stop_time = time.time()  # + 0.3
        resp_time = stop_time - start_time
        app.post_read_db_seconds.observe(resp_time)
        time.sleep(3)

```

### 20.2 How-to start the project

Described in 19.2 and additionally after launching all the applications you need to set up a kibana index pattern for the fluentd

### 20.3 How-to check the project

Go to these links:

* <http://docker_host_ip:9411> - a zipkin web interface

* <http://docker_host_ip:5601> - a kibana web interface

## Homework-21: Introduction to Kubernetes

Main task: do research about the  kubernetes main components, deploy them  by "Hard Way", do research about the main primitives in a Kubernetes

Advanced task *: develop an ansible playbook to install Kubernetes as it described by `Kubernetes The Hard Way`

### 21.1 What was done

* Manually completed the guide `Kubernetes The Hard Way`, checked deployments (ui, post, mongo, comment) and the PODs starting

* Developed the ansible playbooks to automate `Kubernetes The Hard Way`

```bash
02-client-tools.yml
03-create-controller-instance.yml
03-create-worker-instance.yml
03-provisioning-compute-resources.yml
04-certificate-authority.yml
04-copy-creds-to-controller.yml
04-copy-creds-to-worker.yml
04-prepare-node.yml
04-worker-instance-certificate.yml
05-generate-kubeconfigs.yml
05-generate-service-kubeconfig.yml
05-generate-worker-kubeconfig.yml
06-data-encryption.yml
07-bootstraping-etcd.yml
08-bootstrapping-kubernetes-controllers.yml
08-kubernetes-frontend-load-balancer.yml
09-bootstrapping-kubernetes-workers.yml
10-configuring-kubectl.yml
11-pod-network-routes.yml
12-dns-addon.yml
kubernetes_the_hard_way.yml
```

### 21.2 How-to start the project

We assume that a gcloud is already installed and we have a GCP service account

```bash
cd kubernetes/ansible
virtualenv .venv
source .venv/bin/activate
pip install -r requirements.txt
export GCE_REGION=$(gcloud config get-value compute/region 2> /dev/null)
export GCE_CREDENTIALS_FILE_PATH=~/.ansible/gce-service-account.json
export GCE_EMAIL=user@docker-1234.iam.gserviceaccount.com
export GCE_PROJECT=docker-1234
ansible-playbook -K kubernetes_the_hard_way.yml
```

### 21.3 How-to check the project

To check the kubernetes install out:

* Execute the steps described here <https://github.com/kelseyhightower/kubernetes-the-hard-way/blob/master/docs/13-smoke-test.md>

* Check the PODs (`ui, post, mongo, comment`)

```bash
cd kubernetes/reddit
for DEPLOYMENT in *.yml; do kubectl apply -f $DEPLOYMENT;done
```

## Homework-22: Kubernetes. Deploying a cluster and applications. Security model

Main task: deploy the local environment to work with k8s; deploy a k8s cluster to GCE; launch the reddit application in the k8s

Advanced task *: deploy a k8s cluster to GKE by terraform; create the YAML manifests to enable a k8s dashboard

### 22.1 What was done

* Deployed and configured the local environment (minikube)

* Configured the reddit application `deployment` and `service`

* Added dev `namespace` manifest

* Developed the `terraform` configuration to provision GKE - the gke terraform module that deploy a k8s cluster and configure the firewall rules

* Added the YAML manifests to deploy a k8s dashboard

### 22.2 How-to start the project

* Deploy a kubernetes to GKE

```bash
cd kubernetes/terraform
terraform init
terraform apply -auto-approve=true
cd kubernetes
terraform init
terraform apply -auto-approve=true
```

* Configure `kubectl`

```bash
export GKE_CLUSTER=cluster-name-here
export GCP_ZONE=zone-here
export GCP_PROJECT=project-here
gcloud container clusters get-credentials $GKE_CLUSTER --zone $GCP_ZONE --project $GCP_PROJECT
```

* Allow the user to create roles in k8s cluster by set up `name: SETUP_USER_ACCOUNT_HERE` in `kubernetes/reddit/cluster-admin-rolebinding.yml` and then execute:

```bash
kubectl apply -f cluster-admin-rolebinding.yml
```

* Upload a dashboard to the  kubernetes

```bash
kubectl apply -f kubernetes-dashboard.yaml
kubectl apply -f kubernetes-dashboard-rolebinding.yml
```

* Create `dev` namespace

```bash
kubectl apply -f dev-namespace.yml
```

* Deploy the  reddit application to  `dev` namespace

```bash
kubectl apply -f . -n dev
````

### 22.3 How-to check the project

* Check the dashboard out

```bash
kubectl proxy
```

got to link <http://localhost:8001/ui>

* Check the reddit application out

```bash
REDDIT_IP=$(kubectl get nodes  -o json | jq --raw-output --arg ext_ip "ExternalIP" '.items[0].status.addresses[] | select( .type == $ext_ip) | .address')
```

```bash
REDDIT_PORT=$(kubectl get services ui -n dev -o json | jq '.spec.ports[].nodePort')
```

Go to link <http://$REDDIT_IP:$REDDIT_PORT> to access to the application

## Homework-23: Kubernetes. Networks, Storages

Main task: do research about the k8s service types (ClusterIP, NodePort, LoadBalancer) and how they work with `kube-dns`; do research about Ingress to access to cluster resources outside of a cluster, loadbalancing, TLS termination; do research about the networks policies to restrict an access to a mongodb; configure a fast and persistent storage for a mongodb by a persistent volume claim and a storage class

Advanced task *: describe a `Secret` as a manifest

### 23.1 What was done

* Checked out `kube-dns`

* Checked out `ui` service in the `nodePort` mode

* Configured `LoadBalancer` for a TCP loadbalancing and checked how it works

* Instead of `LoadBalancer` (that has limitations) `Ingress controller` was configured to a L7 loadbalancing and a TLS termination

* (*) Secret was described as a manifest (см. `ui-ingress-secret.yml.example`)

* Added `StorageClass` for mongodb

* mongodb storage is connected by `Persistent Volume Claim`

### 23.2 How-to start the project

It is all similar to how it was described 22.2 except after the cluster creation you need to enable `NetworkPolicy`:

```bash
gcloud beta container clusters update <cluster_name_here> --zone=<zone_here> --update-addons=NetworkPolicy=ENABLED
gcloud beta container clusters update <cluster_name_here> --zone=<zone_here> --enable-network-policy
```

and set up `ui-ingress-secret.yml.example` by adding the real certificates and key instead `tls_certificate_here`, `tls_key_here`

### 23.3 How-to check the projects

* To check`Ingress` controller out you need to get the IP address:

```bash
INGRESS_ADDRESS=$(kubectl get ingress -n dev -o json | jq --raw-output '.items[].status.loadBalancer.ingress[].ip')
```

and check that the application is working <https://INGRESS_ADDRESS>

* To check `Persistent Volume Claim` out you need to create a post in the reddit application, remove the mongodb deployment and start the mongodb again:

```bash
kubectl delete deploy mongo -n dev
kubectl apply -f mongo-deployment.yml -n dev
```

the previously created post should be restored

## Homework-24: CI/CD in Kubernetes

Main task: working with helm, deploying a gitlab to a kubernetes, launching a CI/CD pipeline in a Kubernetes

Advanced task *: connect the image building pipeline with the deploying pipeline so after a release of an image from master branch the deploy of the new version was started to production environment

### 24.1 What was done

* Installed helm and tiller

* Developed post, reddit, ui `helm charts`

* gitlab omnibus installed and configured to k8s

* Developed the gitlab pipelines to  `review/stop_review` the microservices

* Developed the pipeline to deploy the  reddit application to the stage/prod environments in the k8s cluster

* (*) The building pipelines and the deploying pipelines are connected

* Added the node_pool (defaultpool, bigpool) to the  terraform configuration to fine tuning GKE. Added provisioner to terraform to set up permissions, installing a gitlab and so on

### 24.2 How-to check the project

We assume that terraform, kubectl, helm are installed on the local host

* Deploy a kubernetes to GKE, tiller and gitlab-omnibus also will be installed

```bash
cd kubernetes/terraform
terraform init
terraform apply -auto-approve=true
cd kubernetes
terraform init
terraform apply -auto-approve=true
```

* Create a group and set up the projects for these microservices: ui, comment, post, reddit-deploy

* Create a trigger for reddit-deploy (which will be used by the other pipelines participants) and save the token to `REDDIT_DEPLOY_TOKEN`

* Add these variables to the group settings in the Gitlab:

```bash
CI_REGISTRY_USER - логин в dockerhub
CI_REGISTRY_PASSWORD - пароль в dockerhub
REDDIT_DEPLOY_TOKEN - - токен для запуска reddit-deploy из других пайплайнов
```

* Push source code of ui, comment, post, reddit-deploy to the gitlab projects:

### 24.3 How-to check the project

* If your changes was occurred not in the `master` branch after building the corresponding microservice  `environments` will contain a link to `review`.

* If your changes occurred in the `master` branch for the first the build pipeline will be launched to build the corresponding microservice and then the deploy pipeline will be triggered to deploy the stage/prod environments

* To check the list of installed releases:

```bash
helm ls
```

## Homework-25: Kubernetes. Monitoring and logging

Main task: deploying a prometheus to a k8s, set up a prometheus and a grafana to collect metrics, set up EFK to collect logs

Advanced task *: install an alertmanager to k8s and set up the k8s api server and hosts availability rules

Advanced tasks *: create a helm chart to install EFK stack

### 25.1 What was done

* Disabled stackdriver

* Added a prometheus helm with a kube-state-metrics and a node-exporter

* Added `reddit-production, post-endpoints, comment-endpoints, ui-endpoints` jobs to a prometheus helm chart

* Added a grafana installation to the k8s bootstrapping process

* Parametrization via namespaces for `Business_Logic_Monitoring, Post_DB_stats, UI_Service_Monitoring` grafana dashboard

* Added the new `kubernetes cluster monitoring, Kubernetes deployment metrics` grafana dashboards

* (*) Enabled alertmanager in the prometheus helm chart, added the  `NodeDow`, `APIServerDown` alerts

* (*) Developed the EFK helm chart, added EFK installation to the k8s bootstrapping process

### 25.2 How-to start the project

We assume that terraform, kubectl, helm are installed on the local host

* Deploy a kubernetes in GKE and tiller, prometheus, alertmanager, grafana, EFK will be deployed automatically

```bash
cd kubernetes/terraform
terraform init
terraform apply -auto-approve=true
cd kubernetes
terraform init
terraform apply -auto-approve=true
```

* After the cluster bootstrapping create the `Prometheus server` datasources in the grafana and import `Business_Logic_Monitoring, Post_DB_stats, UI_Service_Monitoring, Kubernetes cluster monitoring, Kubernetes deployment metrics` dashboards from `monitoring/grafana/dashboards` directory

* Create index `fluentd-*` in the kibana

### 25.3 How-to check the project

* Get an external IP address of applications and add it to a hosts file:

```bash
export HOSTS_ENTRY="$(kubectl get svc | grep nginx-nginx-ingress-controller | awk '{print $4}') reddit-prometheus reddit-grafana reddit-kibana"

echo "$HOSTS_ENTRY" | sudo tee -a /etc/hosts
```

go to the links <http://reddit-prometheus>, <http://reddit-grafana>, <http://reddit-kibana> to access the prometheus, grafana, kibana respectively

* Launch some instances of the reddit application

```bash
helm upgrade reddit-test ./reddit —install
helm upgrade production --namespace production  ./reddit --install
helm upgrade staging --namespace staging  ./reddit —instal
```

* In the grafana dashboards `Business_Logic_Monitoring, Post_DB_stats, UI_Service_Monitoring` you can select the corresponding namespace and get the metrics of the reddit application only for this namespace

* Grafana dashboards `Kubernetes cluster monitoring, Kubernetes deployment metrics` show the current state of the k8s cluster

* If the k8s node is failed  (for instance, after a shutdown) the alert `NodeDown` will be sent to the slack channel and the email

* You can access to the logs of the reddit application in the kibana web interface
