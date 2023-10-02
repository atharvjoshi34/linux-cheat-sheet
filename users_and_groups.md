# Managing Users in Linux 

1. **useradd** - This command will create the user in the system. Only admins are allowed to make user. The sample command would make the user u1. Sample ->  **useradd u1**.
2. **passwd** - This command is used to change or delete the password of a particular user. As we saw in the previous command we made a user u1 now you be knowing the password for user u1. So for that you can do two things.
- **passwd -d u1** - this command will delete the password that is being set for the user us. **Note - This command will delete the password set on the user and user would be able to login without any password. Not a good pratice**
- **passwd u1** - This will change the password for the user u1.
3. **-c** - This flag is used to provide the comment for the user. That is the fifth field in the below format
4. **-d** - This flag is useed to change the default user directory of the user.
5. **-u** - this is used to assign a uid to the user
6. **-g** - This flag is used to assign a particular group to the user
7. **userdel** - This command will delete the user that is mentioned. This command dont delete the user home directory. To do that user the flag **-r** 


  
#### Details of a user are located in the file /etc/passwd.

When you will open the above file you will see the details in the following format **u1:x:1001:1001::/home/u1:/bin/bash**

- **u1** - The first field represent the username in our case which is u1.
- **x** - The second field represent the password of the user. It is stated as x as passwd wont be revealed anyone who will look at this file
- **1001** - the third field is the uid of the user.
- **1001** - the foruth field would be the group id.
- **::** - The fifth field is comment which is currently empty in our case
- **/home/u1** - the sixth field is the user home directory
- **/bin/bash** - The seventh and the last field is shell name the use can access
