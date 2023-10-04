# Logical Volmue Management in Linux

Attaching a Screenshot to better understand in a visual way what we mean by logical volume management
***

![image](https://github.com/atharvjoshi34/linux-cheat-sheet/assets/109728276/f0f192f4-3aef-42ef-bcfe-81916a5522d1)

***

1. As you can see in the Screenshot first step is the create the the physical volumes from the the actual phsycial devices that are available to use
- To create a physical volume you need to use the command **pvcreate**. Sample -> **pvcreate /dev/disk_name**. As in the screenshot we can see we have three physical devices to convert into physical volume so you need to run this command three times.

***

2. Now that you have created the physical volume you need to club them into a volume group. In this scenario we can combine all the three phsycial volume to make a single volume group.
- To create a volume group you need to use the command **vgcreate name_of_volume_group /dev/disk_name /dev/disk_name**. Sample -> **vgcreate vg1 /dev/sda1 /dev/sda2**
- **vgs** - You can run this command to see the newly created volume group

***

3. Now to create the logical volume you need to run the command **lvcreate -L size -n NAME Volume_group_name**. L is for mentioning the size, n is for name. Sample -> **lvcreate -L 8 -n lv1 vg1**.
- Note: Always take a bit more size of whatever u need to make

***

4. Just like the partition we need to mount this as well. To do that open the file **/etc/fstab** and make the entry in the following format.
- **/dev/volume_group/Logical_volume mount_point format defaults 0 0**. Sample -> **/dev/vg1/lv1 /lv xfs deafults 0 0**

***

5. Now you need to format it first using the command **mkfs.format /dev/volume_group/logcial_volume**. Sample -> **mkfs.xfs /dev/vg1/lv1**

***
6. Now we may need to increase the logical volume size. There can be two scenario in this case. First one in which the volume group has the space available and vice verse.
- Now to extend the volume in the first case run the command **lvextend -r -L +/- /dev/volume_group/logcial_volume**. r flag is used to tell the command that we need to use the same file system that we are using, L flag is used to tell the size if we are extending we will use + sign. Sample -> **lvextend -r -L +2Gb /dev/vg1/lv1**

***

7. If you dont have enough space then first you need to extend the volume group and to do that the command would be **vgextend NAME /dev/disk_name**. Then run the above procedure again

***

8. The default extend size is 4Mb to change it use the command **vgcreate -s 8M /dev/disk_image**

***
