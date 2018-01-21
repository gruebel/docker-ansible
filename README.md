# Ansible

[![Build Status](https://travis-ci.org/gruebel/docker-ansible.svg?branch=master)](https://travis-ci.org/gruebel/docker-ansible)
[![Docker Automated build](https://img.shields.io/docker/automated/gruebel/ansible.svg)](https://hub.docker.com/r/gruebel/ansible/builds/)

## Overview
A small image based on the offical Python Alpine image.
Right now there is only the AWS variant, but soon there will also be an Azure one.
For more information on Ansible check out their [website](https://www.ansible.com/)!

## Development
### Pip package version check
To check for any outdated pip packages run following command

```bash
$ docker run --rm -it --entrypoint='' gruebel/ansible:aws pip list --outdated --format=columns
```
