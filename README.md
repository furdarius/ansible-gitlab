# Ansible Role: GitLab
[![Build Status](https://travis-ci.org/Furdarius/ansible-gitlab.svg?branch=master)](https://travis-ci.org/Furdarius/ansible-gitlab)

Start Gitlab Omnibus service as Docker container.

## Variables

All variables can be found in [defaults/main.yml](https://github.com/Furdarius/ansible-gitlab/blob/master/defaults/main.yml)

SSL Certificates for Gitlab and Docker-Registry automaticaly will be imported from
`gitlab_cers_folder` path. This folder should contain 2 certs:
`gitlab.example.com.crt`, `registry.example.com.crt`.

## Requirements

* Docker engine [installed](https://docs.docker.com/engine/installation/) on remote machine.
* `docker-py >= 1.10.6`

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
