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

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/6531cac6-f0ca-4b1e-a5e1-dd1189e9cea2)

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/98d17a97-0e61-4dcd-8916-0c631575c117)

##### Add a User (Simulate) under a team ex: Nitish added to team1 Ensure below constraints are met:

- ansible all -m user -a "name=Nitish2 group=NinjaTeam state=present" -b 

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/73d114ec-1f1d-4ad6-b331-3042faf13949)

##### User Nitish2 has been created under group NinjaTeam

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/fbef47cc-8bab-487f-81a0-ca2cbc75e73e)

#### A user should have read,write, execute access to home directory

- ansible all -m file -a "path=/home/Nitish2 state=directory mode=0755" -b

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/33591e2c-af54-468f-bb81-47af53610f21)

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/90bfa9a4-c3be-4566-a7b4-81e9aa8d6dd7)

##### All the users of same team should have read and excute access to home directory of fellow team members.

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/90bfa9a4-c3be-4566-a7b4-81e9aa8d6dd7)

##### In home directory of every user there should be 2 shared directories

##### Team: Same team members will have full access

- ansible all -m file -a "path=/etc/skel/team state=directory mode=0777" -b

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/8874577e-6678-4d8f-87f8-ddde10fce99f)

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/200d4ff6-379b-4659-928b-58496c38752c)

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/8595ceb4-23d1-490c-a6e1-33b315812b9c)

##### Ninja: All ninja's will have full access

- ansible all -m file -a "path=/etc/skel/ninja state=directory mode=0777" -b

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/eff3dc77-3c4a-4c35-855c-5f47a63496ac)

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/200d4ff6-379b-4659-928b-58496c38752c)

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/8595ceb4-23d1-490c-a6e1-33b315812b9c)

### Additional Features:

##### Changing shell for user

- ansible all -m user -a "name=Nitish2 shell=/bin/bash state=present" -b    

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/7c43cf39-7a99-4a40-ae9c-6a465232ee8b)

##### Shell has been changed

![image](https://github.com/LuckyJayanth/jayanth/assets/153024353/f9836f3a-634c-4749-9207-8093d79f1805)

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
