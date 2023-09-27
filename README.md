# Basic Linux Commands 

1. **touch**  - This command is use to create a file.The command to create a file name one would be  Sample -> **touch one**

---

2. **mkdir** - This command will make the directory. To make a directory inside a directory use the -p flag.The sample command will make directory A insdie their would be another directory b then C. Sample -> **mkdir A/B/C**

---
3. **rm** - This command is used to delete files. You can delete the directory with it using -r flag. Lets suppose there is directory whose structure is A/B/C now to delete all sub directory of A you can use the sameple command. Sample -> **rm -r A**

---
4. **cp** - This command is used to copy files and paste them to the destination you want. The command follow the structure like **cp sources destination**. There can be mulitple sources at once. Sample command will show you how you can copy two files named file1, file2 to folder B that is inside A. Sample -> **cp file1 file2 A/B**

---
5. **mv** - This command is used to move files from one place to another. It can also be used to rename the file. The two sample command will show you how to move file1, file2 to folder b and renaming the file3 to file4. Sample 1 -> **mv file1 file2 A/B**  Sample 2 -> **mv file3 file4**

---
6. **find** - This comamnd is used to find the file in your system. The structure of this command goes as **find source -parameter file_name**. In this source is the place where you want to search parameter is the criteria by which u want to search there can be manay parameters to know more about them you can run the command **man find** to read the documentation. The sample command will show you how you can find the file named file1 in the current working directory. Sample -> **find . -name file1**

---
> ### Questions Based on the Basic linux commands
> 
> **A. Find all the files owened by user "root" and copy them to the directory /mnt/copy.**
>
> NOTE - First try this with logging as root user
>
> Answer: **find . -user root -exec cp {} /mnt/copy \;**


---
# Essential Linux Tools 

1. ****
