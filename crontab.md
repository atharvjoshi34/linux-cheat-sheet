# Crontab command in Linux 

![Screenshot (101)](https://github.com/atharvjoshi34/linux-cheat-sheet/assets/109728276/3b73e6d7-ca56-462c-bb6b-a7380fe4f058)

To schedule a task using a crontab you need to tell at which time you need to run it and it follows a specific format which you can see in the screenshot.

1. Step one would be to check whether the cron service is running or not. To do that run the command **service cron status**. If it is not and you want to install cron on your system( centos) follow instrcution on this [link](https://webhostinggeeks.com/howto/how-to-install-crontab-on-centos-6-2/)
2. Step two run the command **crontab -e**. When you run this command you will enter the crontab file where u need to mentioned the content in the following order of screenshot.
3. To delete all the entry in the crontab use the command **crontab -r**
