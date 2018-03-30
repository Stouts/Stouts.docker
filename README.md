Stouts.docker
=============

Ansible role to install and setup docker

#### Variables

```yaml
docker_enabled: yes                         # Enable the role
docker_setup: yes                           # Install docker and dependencies
docker_run: yes                             # Setup docker images/containers/networks

docker_api_version: 1.18
docker_opts: "--dns 8.8.8.8 --dns 8.8.4.4"  # Docker command line options
docker_keyserver:  hkp://p80.pool.sks-keyservers.net:80
docker_keysig: 58118E89F3A912897C070ADBF76221572C52609D
docker_repo: deb https://apt.dockerproject.org/repo {{ ansible_distribution|lower }}-{{ ansible_distribution_release|lower }} main
docker_compose_release: "https://github.com/docker/compose/releases/download/1.6.2"   # Install docker-compose (set empty to skip)

docker_users: []                            # List of usernames to add in docker group
docker_python: no                           # Install docker-py
docker_python_version: 1.10.6

docker_images: []                           # List of docker images to load (required docker_python enabled)
docker_containers: []                       # List of docker containers to run
                                            # docker_run:
                                            #   - name: something
                                            #     image: someuser/someimage
                                            #     ... (see ansible docker_container module)
docker_networks: []                         # List of docker networks to create
                                            # docker_networks:
                                            #   - name: something
                                            #     image: someuser/someimage
                                            #     ... (see ansible docker_container module)

docker_containers_remove: []
docker_images_remove: []
docker_networks_remove: []

docker_logins: []                           # List of docker registries to login
                                            # docker_logins:
                                            #   - registry: docker.registry.com
                                            #     username: username
                                            #     password: password
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
