# Ansible Role to install Docker

Tested on:
- CentOS 7
- Debian Jessie
- Debian Stretch
- Ubuntu Xenial
- Ubuntu Bionic

Example usage is included in `vagrant.yml`.

## Attention

Managing docker volumes is smh fucked up due to some weird python issues. Use with caution.

## Docker Confuguration

The `daemon.json` file is assembled from the `docker_config` variable.
See `defaults/main.yml` for examples.
For configuration options see the [docker docs](https://docs.docker.com/engine/reference/commandline/dockerd/).
The default values for this role are the docker daemon default values.

## Managing the docker group

When `docker_manage_group` is true a group named after the `docker_group` variable will be created.
The variable `docker_users` can be defined as a list of users added to this group.

## Managing docker networks

The variable `docker_networks` can be defined as a list of docker networks.
It accepts the same parameters as the ansible docker_network module.
For options see the [ansible docs](https://docs.ansible.com/ansible/2.5/modules/docker_network_module.html).

## Managing docker volumes

The variable `docker_volumes` can be defined as a list of docker volumes.
It accepts the same parameters as the ansible docker_volume module.
For options see the [ansible docs](https://docs.ansible.com/ansible/2.5/docker_volume_module.html).

## Managing docker containers

The variable `docker_containers` can be defined as a list of docker containers.
It accepts the same parameters as the ansible docker_container module.
For options see the [ansible docs](https://docs.ansible.com/ansible/2.5/docker_container_module.html).
