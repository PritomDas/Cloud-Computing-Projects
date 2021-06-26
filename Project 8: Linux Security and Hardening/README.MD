<!-- PROJECT LOGO -->
<br />

<p align="center">
  <img src="./images/1.jpg" alt="Logo" width="600" height="600">
</p>


> Linux, Linux System Administration, Linux Secrutiy, Hardening Linux System
<!-- ABOUT THE PROJECT -->

# Securing and Hardening a Linux System

## Project Description




<!-- Linux Theory -->
### Basic Commands for Linux

<details>
<summary>ls</summary><br><b>

The ls command is used to list files or directories in Linux and other Unix-based operating systems. Just like you navigate in your File explorer or Finder with a GUI, the ls command allows you to list all files or directories in the current directory by default, and further interact with them via the command line.

</b></details>

<details>
<summary>cd</summary><br><b>

The cd command will allow you to change directories. ... To navigate into the root directory, use "cd /" To navigate to your home directory, use "cd" or "cd ~" To navigate up one directory level, use "cd .." To navigate to the previous directory (or back), use "cd -"
</b></details>

<details>
<summary>mkdir</summary><br><b>

The mkdir command in the Unix, DOS, DR FlexOS, IBM OS/2, Microsoft Windows, and ReactOS operating systems is used to make a new directory.
</b></details>

<details>
<summary>touch</summary><br><b>

The touch command is a command line utility to update timestamps on files. UNIX and UNIX like operating systems store timestamp information for each file or folder including access time, modify time and change time. It is possible to modify timestamps using the touch command either to update a timestamp to the current time or to modify it to a date in the past.
</b></details>

<details>
<summary>cp</summary><br><b>

cp stands for copy. This command is used to copy files or group of files or directory. It creates an exact image of a file on a disk with different file name. cp command require at least two filenames in its arguments.
</b></details>

<details>
<summary>mv</summary><br><b>

The mv command (short from move) is used to rename and move and files and directories from one location to another. 
</b></details>

<details>
<summary>rm</summary><br><b>

rm stands for remove here. rm command is used to remove objects such as files, directories, symbolic links and so on from the file system like UNIX. To be more precise, rm removes references to objects from the filesystem, where those objects might have had multiple references (for example, a file with two different names). By default, it does not remove directories.
</b></details>


<details>
<summary>useradd</summary><br><b>
Only root or users with sudo privileges can use the useradd command to create new user accounts. When invoked, useradd creates a new user account according to the options specified on the command line and the default values set in the /etc/default/useradd file.
</b></details>


<details>
<summary>usermod</summary><br><b>
usermod command or modify user is a command in Linux that is used to change the properties of a user in Linux through the command line. After creating a user we have to sometimes change their attributes like password or login directory etc. so in order to do that we use the Usermod command. The infomration of a user is stored in the following files:

* /etc/passwd
* /etc/group
* /etc/shadow
* /etc/login.defs
* /etc/gshadow
* /etc/login.defs
  
When we execute usermod command in temrinal the command make the changes in these files itself.
</b></details>

<details>
<summary>groupadd</summary><br><b>
Groups in Linux refer to the user groups. In Linux, there can be many users of a single system, (normal user can take uid from 1000 to 60000, and one root user (uid 0) and 999 system users (uid 1 to 999)). In a scenario where there are many users, there might be some privileges that some users have and some don’t, and it becomes difficult to manage all the permissions at the individual user level. So using groups, we can group together a number of users, and set privileges and permissions for the entire group. groupadd command is used to create a new user group.
</b></details>

<details>
<summary>sudo</summary><br><b>
If you prefix “sudo” with any linux command, it will run that command with elevated privileges.  Elevated privileges are required to perform certain administrative tasks.  Someday you may wish to run a LAMP (Linux Apache MySQL PHP) server, and have to manually edit your config files.  You might also have to restart or reset the Apache web server or other service daemons.  You even need elevated privileges to shutdown or restart the computer. 
</b></details>

<details>
<summary>xxx</summary><br><b>

</b></details>


<details>
<summary>xxx</summary><br><b>

</b></details>


<details>
<summary>xxx</summary><br><b>

</b></details>


<details>
<summary>xxx</summary><br><b>

</b></details>











### Basic Linux Knowledge

<details>
<summary>PAM</summary><br><b>

Linux Pluggable Authentication Modules (PAM) is a suite of libraries that allows a Linux system administrator to configure methods to authenticate users. It provides a flexible and centralized way to switch authentication methods for secured applications by using configuration files instead of changing application code. There are Linux PAM libraries allowing authentication using methods such as local passwords, LDAP, or fingerprint readers. Linux PAM is evolved from the Unix Pluggable Authentication Modules architecture.
  
Linux-PAM separates the tasks of authentication into four independent management groups:

* account modules check that the specified account is a valid authentication target under current conditions. This may include conditions like account expiration, time of day, and that the user has access to the requested service.
* authentication modules verify the user's identity, for example by requesting and checking a password or other secret. They may also pass authentication information on to other systems like a keyring.
* password modules are responsible for updating passwords, and are generally coupled to modules employed in the authentication step. They may also be used to enforce strong passwords.
* session modules define actions that are performed at the beginning and end of sessions. A session starts after the user has successfully authenticated.

</b></details>


### Sytem Hardening- The core principles:
To improve the security level of a system, we take different types of measures. This could be the removal of an existing system service or uninstall some software components. System hardening is the process of doing the ‘right’ things. The goal is to enhance the security level of the system. There are many aspects to securing a system properly. Yet, the basics are similar for most operating systems. So the system hardening process for Linux desktop and servers is that that special.

The core principles of System Hardening:

* Principe of least privilege: it means that you give users and processes the bare minimum of permission to do their job. It is similar to granting a visitor access to a building. You could give full access to the building, including all sensitive areas. The other option is to only allow your guest to access a single floor where they need to be. Eg: When read-only access is enough, don’t give write permissions

* Segmentation: means that you split bigger areas into smaller ones. If we look at that building again, we have split it into multiple floors. Each floor can be further divided into different zones. Maybe you visitor is only allowed on floor 4, in the blue zone. If we translate this to Linux security, this principle would apply to memory usage. Each process can only access their own memory segments.
* Reduction: This principle aims to remove something that is not strictly needed for the system to work. It looks like the principle of least privilege, yet focuses on preventing something in the first place. A process that does not have to run, should be stopped. Similar for unneeded user accounts or sensitive data that is no longer being used.



<!-- CONTACT -->

## Contact

Pritom Das Radheshyam - [Portfolio Website](https://pritom.uwu.ai/)
[![LinkedIn][linkedin-shield]][linkedin-url]  





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/you-found-pritom
[product-screenshot]: images/screenshot.jpg

