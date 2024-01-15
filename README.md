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

![IMG_20240115_172424 (1)](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/cdb8d65a-74b6-4423-b9ee-cdffcae32b21)


## Execution of playbook

![IMG_20240115_183705](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/ff9b8b08-677b-4d7d-a662-7bf49ec3123d)


## nginx successfully installed
![2 1](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/6ed57975-103c-4714-8aad-ff0eb2efbd3d)



## Connection is successful with the pubilc IP in browser

![2 2](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/9704e363-4cd2-4fb4-bdc2-b9c736c90e3d)


