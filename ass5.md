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

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/a5fa4369-114f-4a10-afa8-b2fc0e502d22)

## Connection is successful with the pubilc IP in browser

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/a2fd65e3-69f7-44c2-963a-0e685cd4a5a1)

