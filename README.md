## Ubuntu 16.04 docker image for testing ansible roles

[![Build Status](https://travis-ci.org/lestex/docker-ubuntu1604-ansible.svg?branch=master)](https://travis-ci.org/lestex/docker-ubuntu1604-ansible)

### How to Build

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. clone this repo
  3. `cd` into `docker-ubuntu1604-ansible`.
  4. Run `docker build -t ubuntu1604 .`

### How to run

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull lestex/docker-ubuntu1604-ansible`. Use the `latest` tag.
  3. Run a container from the image: 
  ```
  docker run -p --name test --privileged -v=/sys/fs/cgroup:/sys/fs/cgroup:ro lestex/docker-ubuntu1604-ansible /lib/systemd/systemd
```
  4. Use Ansible inside the container:
  
```
docker exec -it test ansible --version
docker exec -it test ansible-lint /path/to/ansible/playbook.yml
```

### Author

Created by Andrey Larin.
