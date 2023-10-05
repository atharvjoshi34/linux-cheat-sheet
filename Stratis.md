# Stratis

1. To install stratis run the following command **yum install stratis-cli stratisd**
2. After installing it enable and start the stratisd deamon. Sample -> **systemctl start/enable stratisd**
3. First step would be to create a pool and command to do this -> **stratis pool create pool_name /dev/disk_name**
4. Now to increase the size of this pool you can run this command to do that -> **stratis pool add-data pool_name /dev/disk_name**
5. You can create n number of filesystem from this pool. To do that run the command -> **stratis filesystem create pool_name file_system_name**
6. Then run the command **stratis filesystem list** and copy the uid
7. Mount this as well just like we did for the partition and logical volume and instead of the path use uid, in the default field wirte **default,x-systemd.requires=stratisd.service**

# Virtual Data Optimizer

1. To install VDO run the command **yum install vdo kmod-kvdo**
2. To create a VDO command is **vdo create --name NAME --device=/dev/disk_name --vdoLogicalSize=SIZE**
3. To format VDO in specific format run the command **mkfs.FORMAT /dev/mapper/NAME_OF_VDO**
4. Then you need to mount it so go to /etc/fstab  everything will be same as we mentioned in the partitioning one just change the default to **default,x-systemd.requires=vdo.service**
