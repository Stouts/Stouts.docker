Stouts.docker
=============

Ansible role to install and setup docker

#### Variables

```yaml
docker_enabled: yes                         # Enable the role
docker_api_version: 1.18
docker_opts: "--dns 8.8.8.8 --dns 8.8.4.4"  # Docker command line options
docker_keyserver:  hkp://p80.pool.sks-keyservers.net:80
docker_keysig: 58118E89F3A912897C070ADBF76221572C52609D
docker_repo: deb https://apt.dockerproject.org/repo {{ ansible_distribution|lower }}-{{ ansible_distribution_release|lower }} main

docker_users: []                            # List of usernames to add in docker group
docker_python: no                           # Install docker-py

docker_images: []                           # List of docker images to load (required docker_python enabled)
```

#### Usage

Add `Stouts.docker` to your roles

Example:

```yaml

- hosts: all

  roles:
  - Stouts.docker
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.docker/issues)!
