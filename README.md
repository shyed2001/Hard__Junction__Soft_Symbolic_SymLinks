--- 
Title : Hard Links and Soft Symbolic Links .

Lesson 1 : How to Create Hard Links and Soft Symbolic Links in Windows .

Lesson 2 : How to Create Hard Links and Soft Symbolic Links in linux.

Lesson 3 : 7 Key Differences Between Hard link and Soft link.

Author : Shyed Shahriar Housaini.

Date : 07/07/2021 

--- 

> # How to Create Soft and Hard Symbolic Links in Windows


A symbolic link is a file-system object (file or directory) that points to another file system object (file or directory). The object being pointed to is called the target.

There are two type of symbolic links: hard and soft.

A soft link is referenced as a symbolic link and works similarly to a standard shortcut. Soft links will have a shortcut arrow icon on them. For example, when you open a soft link to a folder, you will be redirected to the folder where the files are stored.

A hard link makes it appear as though the file or folder actually exists at the location of the symbolic link, and your app won’t know any better. That can make hard symbolic links more useful in most situations. Hard links to a file will not have a shortcut arrow icon on them.


> ## See also:

* Symbolic Links - Windows applications | Microsoft Docs
* Hard Links and Junctions | Microsoft Docs
* NTFS symbolic link - Wikipedia
* Hard link - Wikipedia
* mklink | Microsoft Docs
* New-Item | Microsoft Docs


A symbolic link can be helpful if say you wanted to sync a folder for a program. For example, if you have a program that must have its files stored at C:\Program Files and you want them stored at D:\My Location instead. You could move the original directory from C:\Program Files to D:\My Location, and create a symbolic link (soft or hard) at C:\Program Files (link) pointing to D:\My Location (target).

This tutorial will show you how to create soft and hard symbolic links (symlinks) pointing to a file or folder in Windows 7, Windows 8, and Windows 10.

If you have Developer Mode turned on in Windows 10, you will need to use the mklink command in a normal command prompt instead of the usually required elevated command prompt.




> # Contents

>Option One: Create Soft Symbolic Link Pointing to File in Command Prompt

> Option Two: Create Soft Symbolic Link Pointing to Directory in Command Prompt

> Option Three: Create Hard Link Pointing to File in Command prompt

> Option Four: Create Hard Link (Junction) Pointing to Directory in Command Prompt

> Option Five: Create Soft Symbolic Link Pointing to File in PowerShell

> Option Six: Create Soft Symbolic Link Pointing to Directory in PowerShell

> Option Seven: Create Hard Link Pointing to File in PowerShell

> Option Eight: Create Hard Link (Junction) Pointing to Directory in PowerShell

> Option Nine: Delete Hard or Soft Symbolic Link 
 


> ## OPTION ONE
Create Soft Symbolic Link Pointing to File in Command Prompt

1 Open an elevated command prompt.

2 Type the command below into the elevated command prompt, and press Enter. (see screenshot below)

mklink "Link" "Source Target"

Substitute Link in the command above with the full path with file name and extension you want created as a soft symbolic link at.

Substitute Source Target in the command above with the full path of the file with extension that is the target (source) you want the soft symbolic link pointing to. This is the actual location where everything will be saved at.

For example: 
```shell
> mklink "C:\Users\Brink\Desktop\My Documents Link.txt" "C:\Users\Brink\Documents\My Document.txt"
```

3 When finished, you can close the elevated command prompt if you like.



> ## OPTION TWO
Create Soft Symbolic Link Pointing to Directory in Command Prompt

1 Open an elevated command prompt.

2 Type the command below into the elevated command prompt, and press Enter. (see screenshot below)

mklink /d "Link" "Source Target"

Substitute Link in the command above with the full path of a folder (directory) you want created as a soft symbolic link at.

Substitute Source Target in the command above with the full path of the folder (directory) that is the target (source) you want the soft symbolic link pointing to. This is the actual location where everything will be saved at.

For example:
```shell
>  mklink /d "C:\Program Files\Mozilla Firefox" "D:\Mozilla Firefox"
```

3 When finished, you can close the elevated command prompt if you like.




> ## OPTION THREE
Create Hard Link Pointing to File in Command Prompt

1 Open an elevated command prompt.

2 Type the command below into the elevated command prompt, and press Enter. (see screenshot below)

mklink /h "Link" "Source Target"

Substitute Link in the command above with the full path with file name and extension you want created as a hard link at.

Substitute Source Target in the command above with the full path of the file with extension that is the target (source) you want the hard link pointing to. This is the actual location where everything will be saved at.

For example:
```shell
>  mklink /h "C:\Users\Brink\Desktop\My Documents Link.txt" "C:\Users\Brink\Documents\My Document.txt"
```

3 When finished, you can close the elevated command prompt if you like.

Create Soft and Hard Symbolic Links in Windows-hard_link_to_file_command_prompt.jpg


> ## OPTION FOUR
Create Hard Link (Junction) Pointing to Directory in Command Prompt

1 Open an elevated command prompt.

2 Type the command below into the elevated command prompt, and press Enter. (see screenshot below)

mklink /j "Link" "Source Target"

Substitute Link in the command above with the full path of a folder (directory) you want created as a hard link at.

Substitute Source Target in the command above with the full path of the folder (directory) that is the target (source) you want the hard link pointing to. This is the actual location where everything will be saved at.

For example:

```shell
>  mklink /j "C:\Program Files\Mozilla Firefox" "D:\Mozilla Firefox"
```

3 When finished, you can close the elevated command prompt if you like.

Create Soft and Hard Symbolic Links in Windows-hard_link_to_directory_command_prompt.png


> ## OPTION FIVE
Create Soft Symbolic Link Pointing to File in PowerShell

1 Open an elevated PowerShell.

2 Type the command below into the elevated PowerShell, and press Enter. (see screenshot below)

New-Item -ItemType SymbolicLink -Path "Link" -Target "Source Target"

Substitute Link in the command above with the full path with file name and extension you want created as a soft symbolic link at.

Substitute Source Target in the command above with the full path of the file with extension that is the target (source) you want the soft symbolic link pointing to. This is the actual location where everything will be saved at.

For example: 
```shell
> New-Item -ItemType SymbolicLink -Path "C:\Users\Brink\Desktop\My Documents Link.txt" -Target "C:\Users\Brink\Documents\My Document.txt"
```

3 When finished, you can close the elevated PowerShell if you like.

Create Soft and Hard Symbolic Links in Windows-soft_symbolic_link_to_file_powershell.jpg


> ## OPTION SIX
Create Soft Symbolic Link Pointing to Directory in PowerShell

1 Open an elevated PowerShell.

2 Type the command below into the elevated PowerShell, and press Enter. (see screenshot below)

New-Item -ItemType SymbolicLink -Path "Link" -Target "Source Target"

Substitute Link in the command above with the full path of a folder (directory) you want created as a soft symbolic link at.

Substitute Source Target in the command above with the full path of the folder (directory) that is the target (source) you want the soft symbolic link pointing to. This is the actual location where everything will be saved at.

For example:

```shell
>  New-Item -ItemType SymbolicLink -Path "C:\Program Files\Mozilla Firefox" -Target "D:\Mozilla Firefox"
```

3 When finished, you can close the elevated PowerShell if you like.

Create Soft and Hard Symbolic Links in Windows-soft_symbolic_link_to_directory_powershell.jpg



> ## OPTION SEVEN
Create Hard Link Pointing to File in PowerShell

1 Open an elevated PowerShell.

2 Type the command below into the elevated PowerShell, and press Enter. (see screenshot below)

New-Item -ItemType HardLink -Path "Link" -Target "Source Target"

Substitute Link in the command above with the full path with file name and extension you want created as a hard link at.

Substitute Source Target in the command above with the full path of the file with extension that is the target (source) you want the hard link pointing to. This is the actual location where everything will be saved at.

For example:

```shell
>  New-Item -ItemType HardLink -Path "C:\Users\Brink\Desktop\My Documents Link.txt" -Target "C:\Users\Brink\Documents\My Document.txt"
```

3 When finished, you can close the elevated PowerShell if you like.

Create Soft and Hard Symbolic Links in Windows-hard_link_to_file_powershell.jpg



> ## OPTION EIGHT
Create Hard Link (Junction) Pointing to Directory in PowerShell

1 Open an elevated PowerShell.

2 Type the command below into the elevated PowerShell, and press Enter. (see screenshot below)

New-Item -ItemType Junction -Path "Link" -Target "Source Target"

Substitute Link in the command above with the full path of a folder (directory) you want created as a hard link at.

Substitute Source Target in the command above with the full path of the folder (directory) that is the target (source) you want the hard link pointing to. This is the actual location where everything will be saved at.

For example:

```shell
>  New-Item -ItemType Junction -Path "C:\Program Files\Mozilla Firefox" -Target "D:\Mozilla Firefox"
```

3 When finished, you can close the elevated PowerShell if you like.

Create Soft and Hard Symbolic Links in Windows-hard_link_to_directory_powershell.jpg



> ## OPTION NINE
Delete Hard or Soft Symbolic Link

1 Open File Explorer (Windows 8/10) or Windows Explorer (Windows 7).

2 Navigate to the location of the symbolic link (soft or hard), and delete it. This will not delete the target (source) the symbolic link points to.

Do not delete the target (source) the symbolic link points to. You only want to delete the link itself.

> # Main difference between Soft link and Hard link
> - A hard link points a name to data on a storage device
> - A soft link points a name to another name, that points to data on a storage device.


> # How can I create Symbolic Links in Linux?.

 In this tutorial, you’ll learn how to make multiple file names reference the same file using hard links and symbolic, also called “soft” links. The two common ways of creating multiple names that point to the same file in Linux are:

Creating a soft link (symbolic link) to the file
Creating a hard link to the file.


## Working with Soft link (Symbolic link)
A soft link is a special type of file that points to an existing file or directory. It can be used to link two files on different file systems. A soft link can point to a special file as well.

The ln -s command is used to create a soft link. Let’s consider an example:

In the following example, the ln -s command is used to create a new soft link for the existing file /tmp/file1.txt that will be named to /tmp/file2.txt:


```shell
> $ echo "Hello from file1" > /tmp/file1.txt
> $ ln -s /tmp/file1.txt /tmp/file2.txt
```

Confirm by listing the files:

```shell
> $ ls -l /tmp/file1.txt /tmp/file2.txt
-rw-------. 1 jkmutai jkmutai 17 Feb  4 22:37 /tmp/file1.txt
lrwxrwxrwx. 1 jkmutai jkmutai 14 Feb  4 22:38 /tmp/file2.txt -> /tmp/file1.txt
```

You can see the first character of the long listing for /tmp/file2.txt is l instead of -. This indicates that the file is a soft link and not a regular file. (A d would indicate that the file is a directory.)


Check the contents of the symbolic link file.

```shell
> $ cat /tmp/file2.txt
Hello from file1
```
For directory, use:

```shell
> ln -s /dir /dir2
```
If you delete the original regular file, the soft link will still point to missing file – a “dangling soft link.”


> # Working with Hard Links
Every file in Linux starts with a single hard link. By creating a new hard link to a file, you are creating another name that points to that same data.

The new hard link acts exactly like the original file name. It is hard to tell the difference between the new hard link and the original name of the file. You use the ln command to create a hard link – Another name that points to an existing file.

```shell
> $ echo "Hello World from Hard Link" >/tmp/hello1.txt
> $ ln /tmp/hello1.txt  /tmp/hello2.txt

``` 
Where:

/tmp/hello1.txt is a path to the existing file
/tmp/hello2.txt is the hard link that you want to create.
Use the ls -i option to ls list the files’ inode number. If the inode numbers are the same, the files are hard links pointing to the same data.

```shell
> $ ls -li /tmp/hello1.txt  /tmp/hello2.txt
2591191 -rw-------.  2 jkmutai jkmutai 27 Feb  5 08:16 /tmp/hello1.txt
2591191 -rw-------. 2 jkmutai jkmutai 27 Feb  5 08:16 /tmp/hello2.tx```t

```

--- Let's add third file and recheck ---


```shell
> $ ln /tmp/hello1.txt  /tmp/hello3.txt 
> $ ls -li /tmp/hello1.txt  /tmp/hello2.txt /tmp/hello3.txt 
2591191 -rw-------.  3 jkmutai jkmutai 27 Feb  5 08:16 /tmp/hello1.txt
2591191 -rw-------. 3 jkmutai jkmutai 27 Feb  5 08:16 /tmp/hello2.txt
2591191 -rw-------. 3 jkmutai jkmutai 27 Feb  5 08:16 /tmp/hello3.txt

```

All hard links referencing the same file have the same:

link count
access permissions
user and group ownerships
time stamps
file content
Compare with ones for Soft link:

```shell
> $ ls -li /tmp/file1.txt /tmp/file2.txt /tmp/file3.txt
2442008 -rw-------. 1 jkmutai jkmutai 17 Feb  4 22:37 /tmp/file1.txt
2442949 lrwxrwxrwx.  1 jkmutai jkmutai 14 Feb  4 22:38 /tmp/file2.txt -> /tmp/file1.txt
2601927 lrwxrwxrwx. 1 jkmutai jkmutai 14 Feb  5 08:24 /tmp/file3.txt -> /tmp/file1.txt

```

# 7 Key Differences Between Hard link and Soft link

    1. A hard link is an additional name of the original file which refers inode to access the target file. 
       1.1 In contrast, soft link is distinct to the original file and is an alias to original file but do not uses inode.
    
    2. When an original file gets deleted soft link becomes invalid whereas, a hard link is valid even if the target file is deleted.
    
    3. In Linux, the command used for the creation of hard link is “ln“. As against, the command used for a soft link is “ln -s“.
    
    4. Hard link has same inode number dissimilar to soft link, where target file and its soft link have distinct inode number.
    
    5. Hard links are restricted to its own partitions, but soft links can cover different file systems.
    6. The performance of hard link is better than soft link in some cases.
    
    7. Relative path and absolute path both are allowed in soft links. On the contrary, the relative path is not allowed in a hard link.




