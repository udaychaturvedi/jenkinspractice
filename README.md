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

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/17d4801b-70f4-43fc-bade-bcf988710e86)

## nginx successfully installed

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/a5fa4369-114f-4a10-afa8-b2fc0e502d22)

## Connection is successful with the pubilc IP in browser

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/a2fd65e3-69f7-44c2-963a-0e685cd4a5a1)
