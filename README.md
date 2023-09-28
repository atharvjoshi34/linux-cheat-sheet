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

7. **|** - Pipe is used to attach two commands together in simpler words with the user of pipe you can send the output of first command as an input to the second one. The sample command do the ls in the /etc folder and combine it with the head commad which is used to see the first few entries. Sample ->  **ls -l /etc | head**

***

8.  **>,>>** - Redirection is used to to send the output of some command to another file. When you will use single **>** its gonna remove all the content of the file (if any) and insert the output of the commad you entered. Meanwhile if you gonna  use **>>**  its gonna append the content of the command to the file you mentioned in the command and keep the content as it is. To test this make two files through command you learnt earlier name them as 1.txt and 2.txt enter some content in them then run both sameple command.Sample -> **ls > 1.txt** , **ls >> 2.txt**. In case of first command you will have all the entry of ls command in the file 1.txt only the content that you entered earlier wont be there. Now when you gonna see the file 2.txt it will have the content that you entered plus the output of the ls command. In case you want to redirct the error output you need to use 2 infront of >.Other concept remains the same if you want to append use double >> and if u want to remove everything and input use single >. Sample -> **ls ab 2>> 1.txt**

***

# Changing the permission of the files and directory 

To change the file permission we use the **chmod** command. There are two method through which you can use the chmod command through which you can grant the permission to the files and directories.

1. **Relative Method** - For who you are granting [User(u), Groups(g), Others(o)], what [ Grant(+), Deny(-)] and which permission you are denying or granting [Read(r), Write(w), Execute(x)]
- To check what permission a file currently has run the command **ls -l File_name** the first one would be user,second is for groups and third is for others. Now I did the same for the file 1.txt and i noticed that the user dont have execute(x) permission now to grant that I will run the sample command. Sample -> **chmod u+x 1.txt**
- In the similar way if you want to remove any permission use (-) sign. To grant a permission to all 3 you can use 'a' instead

***

>### Question on Relative Method
>Write the Command to grant the execute permission to all on file F1
>
>Answer: **chmod a+x F1** or **chmod ugo+x F1**

***

2. **Absolute Method**- In this method each permission read, write, excute are giving a number i.e read(4), write(2), execute(1). Suppose you want to give only read permission you will write 4, read+write 6, write+execute 3.
- Lets understand it with an example suppose you have a file lets say file1.txt now you want to give the user - rwx(7) , group - rw(6), others - w(c). Command to do this would be **chmod 762 file1.txt**

***

>### Question on Absoulte Method
>
>Write the command to assign the follwing permission on the directory DD and DD1 using chmod only once. rwx to all user, wx for the group, none for the others
>
>Answer: **chmod 730 DD DD1**

***
