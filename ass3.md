# Spring3HibernateApp Deployment

This Ansible playbook automates the deployment of the Spring3HibernateApp on a specified server.

## Usage

##### Install required packages (MySQL Server, OpenJDK 11, Maven, Tomcat 9, Tomcat 9 Admin)

- mysql version displayed from server
- 
![3 1](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/7eefcf3c-09ac-4b41-a314-790bdbdcc524)



- maven version displayed from server

![3 2](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/649d0379-e6a0-4609-a6b0-351f938b45fd)

- java version displayed from server

![3 3](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/bf42451c-c73c-4652-acf9-971a44dff575)


- tomcat9

![3 4](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/fdfafca2-f4a7-4f84-a47f-759398521d4c)


### This playbook will perform the following tasks:

##### create dir

![3 5](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/31731ee3-fefb-4997-9cbb-b863588ce1a7)


##### Clone this repository: git clone https://github.com/opstree/spring3hibernate

![3 6](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/2ecb4aa5-e5ab-4761-bc6a-25df46a109da)


###### Generate the WAR file using Maven

![3 7](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/3427f58f-c7e6-4d1e-b5cf-f0fef2e256ba)


###### Add roles to tomcat-users.xml for admin and manager access

![3 8](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/ce095b39-6bfd-40df-8ee0-4edbb8ae3fde)

###### Copy the generated WAR file to the Tomcat webapps directory

![3 9](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/7627097f-a1a6-41bd-b59a-7c72c217fd08)


###### Restart Tomcat 9

- restarted

Tomcat User Credentials

The playbook adds the following credentials to tomcat-users.xml:

<role rolename="admin-gui"/>
<role rolename="manager-gui"/>
<user username="tomcat" password="pass" roles="admin-gui,manager-gui"/>



###### Run the Ansible playbook:

ansible-playbook spring3hibernate.yml

![3 10](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/3426a373-b8be-48ab-8c74-41164846531a)


![294031433-c3415561-7e8f-4f17-9949-433e7fe48f14](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/9f0f1cec-f5f4-4fb9-82f6-3322bfa7a1b5)



