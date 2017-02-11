# Ansible Role: GitLab
[![Build Status](https://travis-ci.org/Furdarius/ansible-gitlab.svg?branch=master)](https://travis-ci.org/Furdarius/ansible-gitlab)

Start Gitlab Omnibus service as Docker container.

## Variables

All variables can be found in [defaults/main.yml](https://github.com/Furdarius/ansible-gitlab/blob/master/defaults/main.yml)

SSL Certificates for Gitlab and Docker-Registry automaticaly will be imported from
`gitlab_cers_folder` path. This folder should contain 2 certs:
`gitlab.example.com.crt`, `registry.example.com.crt`.

## Requirements

* [Docker engine](https://docs.docker.com/engine/installation/) >= `1.13.1` installed on remote machine
	* You can use [ansible-docker](https://github.com/Furdarius/ansible-docker) role to install it.
* [docker-py](https://pypi.python.org/pypi/docker-py/1.10.6) >= `1.10.6`
* [python-netaddr](https://pypi.python.org/pypi/netaddr) >= `0.7.19`

## Playbook example

```yaml
---
- hosts: gitlab
  become: true
  roles:
    - gitlab
  vars:
    gitlab_url: "https://gitlab.infr.local"
    registry_url: "https://registry.infr.local"
    gitlab_cers_folder: "./certs_folder_on_local_machine"
  tags:
    - gitlab
```
