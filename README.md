# Ansible Role: GitLab
[![Build Status](https://travis-ci.org/Furdarius/ansible-gitlab.svg?branch=master)](https://travis-ci.org/Furdarius/ansible-gitlab)

Start Gitlab Omnibus service as Docker container.

## Variables

All variables can be found in [defaults/main.yml](https://github.com/Furdarius/ansible-gitlab/blob/master/defaults/main.yml)

## Requirements

Docker engine [installed](https://docs.docker.com/engine/installation/) on remote machine.

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
