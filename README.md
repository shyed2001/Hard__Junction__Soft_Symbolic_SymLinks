--- 
Title : How to Create Soft and Hard Symbolic Links in Windows.

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

