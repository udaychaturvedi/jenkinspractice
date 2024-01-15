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

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/90bfa9a4-c3be-4566-a7b4-81e9aa8d6dd7)

##### In home directory of every user there should be 2 shared directories

##### Team: Same team members will have full access

- ansible all -m file -a "path=/etc/skel/team state=directory mode=0777" -b

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/680212d3-956f-4c8d-9f9a-54d1cad6c6d3)


![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/200d4ff6-379b-4659-928b-58496c38752c)

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/8595ceb4-23d1-490c-a6e1-33b315812b9c)

##### Ninja: All ninja's will have full access

- ansible all -m file -a "path=/etc/skel/ninja state=directory mode=0777" -b

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/8db13008-25c2-4725-90bc-97a5fa66aef0)


![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/cc56f838-9caa-4dd4-b9db-f65da09d1a8d)


![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/8595ceb4-23d1-490c-a6e1-33b315812b9c)

### Additional Features:

##### Changing shell for user

- ansible all -m user -a "name=Nitish2 shell=/bin/bash state=present" -b    

![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/bbea48d2-d355-4829-824d-32825f48ce97)

##### Shell has been changed
![image](https://github.com/udaychaturvedi/jenkinspractice/assets/149717783/9954b4ac-1c3f-4fda-a1e9-c8b1d5bd3f87)



##### Change user password

- ansible all -m user -a "name=Nitish2 update_password=always password={{ newpassword|password_hash('sha512') }}" -b --extra-vars "newpassword=123456"

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/35da1d06-459c-4981-b3c3-8a979dc0b4f6)

Nitish2 password has been changed

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/fa50b095-40b9-412d-890e-6177c422e0de)

# Delete user

ansible all -m user -a "name=Nitish2 state=absent" -b

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/d0b06ff8-c24d-403d-9384-002726cd2e43)

Nitish2 user has been deleted

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/41f92e47-17de-4a80-bfda-accc85bcc655)

###### List user

- ansible all -m shell -a "getent passwd | cut -d: -f1" -b

##### Below is the list of users

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/629f8612-c584-4783-b885-3c99e9e2d1c7)

##### Delete Group

ansible all -m group -a "name=NinjaTeam state=absent" -b

##### group NinjaTeam has been deleted

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/9c9e0e74-25d1-469e-9413-3cde3caa2cc5)

##### NinjaTeam is absent in screenshot

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/a41a5f26-6179-4074-8944-0b2a2dabe3af)
