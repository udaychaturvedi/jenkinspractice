# Ansible Role for Nginx

## Overview

This Ansible role is designed to install and configure Nginx on various Linux distributions. The role is version-specific, OS-independent, and allows users to customize configurations through variables. It utilizes Jinja templates to dynamically update configuration files and includes handlers for separate management of tasks.

## Features

- Installs a specific version of Nginx.
- OS-independent - supports various Linux distributions.
- Variable-based configuration for flexibility.
- Utilizes Jinja templates for dynamic configuration file updates.
- Handlers for separate management of tasks.

## Requirements

- Ansible installed on the control machine.
- Target machines should have SSH access configured.

## nginx_roles structure

![IMG_20240115_190358](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/3f69c247-c669-43af-bb66-b7b993e15d85)


## Execution of playbook
![IMG_20240115_190316](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/42db5eb2-759a-4710-aa65-91c8a16d2b7f)



## nginx successfully installed

![5 1](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/383cea4f-e100-48dd-b732-2d6626b8eac5)

## Connection is successful with the pubilc IP in browser

![5 2](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/0c39cc5c-7f48-44d0-af4b-14239f47e7aa)


