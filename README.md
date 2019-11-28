gitlab_docker_runner
====================

[![Build Status](https://travis-ci.org/andrelohmann/ansible-role-gitlab_docker_runner.svg?branch=master)](https://travis-ci.org/andrelohmann/ansible-role-gitlab_docker_runner)

Install and register a gitlab runner with docker executor.

Requirements
------------

This role requires ubuntu.

Role Variables
--------------

The default set of variables defines the gitlab runner installation and needs at best to be overwritten in group_vars/host_vars

    gitlab_runner_concurrent: 4 # concurrent jobs
    # gitlab_runner_description: "runner.examlpe.com" # gitlab runner name/domain
    # gitlab_runner_token: __REGISTRATION_TOKEN__
    # gitlab_external_url: __GITLAB_URL__
    gitlab_runner_tags:
    - docker
    gitlab_runner_image: docker:latest

The following mandatory variables need to be set in group_vars/host_vars

    gitlab_runner_description: "runner.examlpe.com"
    gitlab_runner_token: __REGISTRATION_TOKEN__
    gitlab_external_url: http://gitlab.example.com

Example Playbook
----------------

    - hosts: gitlab_docker_runner
      roles:
      - andrelohmann.docker
      - andrelohmann.gitlab_docker_runner

License
-------

MIT

Author Information
------------------

https://github.com/andrelohmann
