Stouts.docker
=============

Ansible role to install and setup docker

#### Variables

```yaml
docker_enabled: yes                         # Enable the role

docker_setup: yes                           # Install docker and dependencies
docker_run: yes                             # Setup docker images/containers/networks

docker_edition: ce
docker_repo: "deb [arch=amd64] https://download.docker.com/linux/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} edge"
docker_opts: "--dns 8.8.8.8 --dns 8.8.4.4"  # Docker command line options
docker_apt_key_id: 9DC858229FC7DD38854AE2D88D81803C0EBFCD88
docker_apt_key_url: hkp://pool.sks-keyservers.net

docker_compose_version: "1.21.0"
docker_compose_release: "https://github.com/docker/compose/releases/download/{{docker_compose_version}}"   # Install docker-compose (set empty to skip)

docker_users: []                            # List of usernames to add in docker group
docker_python: no                           # Install docker-py
docker_python_version: 1.10.6

docker_clean: false                         # Setup a cronjob to clean docker

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

docker_logrotate: false                     # Rotate docker logs
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
