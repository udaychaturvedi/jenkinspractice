# Ansible Assignment-01 - User Managment

### Complete the following steps with the help of ansible modules:

### Question

#### UserManager:
- Add NinjaTeam (Simulate Group) ex: team1
- Add a User (Simulate) under a team ex: Nitish added to team1 Ensure below constraints are met:
- A user should have read,write, execute access to home directory
- All the users of same team should have read and excute access to home directory of fellow team members.
- In home directory of every user there should be 2 shared directories
- Team: Same team members will have full access
- Ninja: All ninja's will have full access
### Additional Features:

- Change user Shell
- Change user password
- Delete user
- Delete Group
- List user or Team

## Execution procedure:

##### Add NinjaTeam (Simulate Group) ex: NinjaTeam

- ansible all -m group -a "name=NinjaTeam state=present" -b

##### Group NinjaTeam has been created
![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/fff727aa-b137-4cac-a855-12d126f574cb)


![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/2aae690e-807b-4bca-9633-e00cf4a855c9)


##### Add a User (Simulate) under a team ex: Nitish added to team1 Ensure below constraints are met:

- ansible all -m user -a "name=Nitish2 group=NinjaTeam state=present" -b 

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/17e9e44c-90ce-4796-9e70-b68c21b31969)


##### User Nitish2 has been created under group NinjaTeam

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/a184c122-58c0-4ebe-80cf-f3598b5b6c6d)


#### A user should have read,write, execute access to home directory

- ansible all -m file -a "path=/home/Nitish2 state=directory mode=0755" -b


![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/2bf584ce-2436-47a6-a871-c00dd02fcf1b)

##### All the users of same team should have read and excute access to home directory of fellow team members.


![1 1](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/0dc00120-2033-49db-ba7c-cbf6936ce4ad)

##### In home directory of every user there should be 2 shared directories

##### Team: Same team members will have full access

- ansible all -m file -a "path=/etc/skel/team state=directory mode=0777" -b

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/680212d3-956f-4c8d-9f9a-54d1cad6c6d3)

![1 2](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/21cbfc05-daf0-4c64-b80c-e0c2f3ae02aa)

![1 3](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/1b4201d4-11ce-49dd-93a1-3c5760cf5b21)






##### Ninja: All ninja's will have full access

- ansible all -m file -a "path=/etc/skel/ninja state=directory mode=0777" -b

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/8db13008-25c2-4725-90bc-97a5fa66aef0)


![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/cc56f838-9caa-4dd4-b9db-f65da09d1a8d)

![1 4](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/b0b7b84b-4c98-43f8-9f55-94424e677be1)



### Additional Features:

##### Changing shell for user

- ansible all -m user -a "name=Nitish2 shell=/bin/bash state=present" -b    

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/bbea48d2-d355-4829-824d-32825f48ce97)

##### Shell has been changed
![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/9954b4ac-1c3f-4fda-a1e9-c8b1d5bd3f87)



##### Change user password

- ansible all -m user -a "name=Nitish2 update_password=always password={{ newpassword|password_hash('sha512') }}" -b --extra-vars "newpassword=123456"

![IMG_20240115_192152](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/7f848692-51fa-4181-84df-c64c6fd491ab)


Nitish2 password has been changed

![1 5](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/9b053573-3652-4b6c-91b5-34def3c67738)


# Delete user

ansible all -m user -a "name=Nitish2 state=absent" -b
![a (1)](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/37f8b10e-0f58-4077-80ce-f0dce4861192)


Nitish2 user has been deleted

![1 6](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/b98b2150-1443-47ab-b5f5-43c30a4b5172)


###### List user

- ansible all -m shell -a "getent passwd | cut -d: -f1" -b

##### Below is the list of users

![IMG_20240115_192208](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/52056009-884d-4c38-8c61-d180cfa4f204)

##### Delete Group

ansible all -m group -a "name=NinjaTeam state=absent" -b

##### group NinjaTeam has been deleted
![b (1)](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/4cec790e-c4e9-42a3-a4a0-74453297ccb2)



##### NinjaTeam is absent in screenshot

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/a41a5f26-6179-4074-8944-0b2a2dabe3af)
