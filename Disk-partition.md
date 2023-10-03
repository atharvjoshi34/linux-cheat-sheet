# Disk Partitioning in Linux 

1. **lsblk** - This command is used to see the partition in your system.
2. **fdisk** - this is the utility with which you can do partition and many other things in the system. Sample - > **fdisk /dev/disk_name**
3. After entering the above command you will enter the fdisk utility. To create a new partition press **n** then select the partition number and then the deafult size. For the last sector rememeber to specify the size as in with a **+** sign.
4. **w** - After creating the partition we need to write this disk to the table and to do that use the **w**
5. Now after exiting the command utility of fdisk you need to run the command **partprobe /dev/disk_name**
 
6.  Now you need to mount this disk to a mount point. In RHCSA Exam they will tell you the mount point. Before mounting this we need to format this disk into a particular type otherwise we wont be able to read write in the disk.

7.  To format the disk command is **mkfs.FORMAT_NAME DISK_PATH**. Sample -> **mkfs.xfs /dev/disk_name**

8.  To mount you need to run the command **mount disk_path mount_point** Sample -> **mount /dev/disk_name /newdirectory**

9.  Now to make this persistent you need to edit the file /etc/fstab. In the this you need to enter the line in the follow format **What_you_want_to_mount mount_point format defaults 0 0**. Sample -> **/dev/disk_name /newdirectory xfs defaults 0 0**
10.  Now run the command **mount -a** if you dont recieve any error everything is done correctly

# Swapping in Linux 

1. To check the swap space use the command **free -m**.
2. Follow the same procedure for creating a new swap. use  **L** to list all the hex code and then same process till partprobe. then instead of mkfs use **mkswap /dev/disk_name**
3. In the file /etc/fstab enter the following **what_you_want_to_swap swap swap defaults 0 0**
4. then run the following commnad **swapon -a**. If no error everything is done correctly 
