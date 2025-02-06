# Linux-OS

**What is Operating System?**
```
  - The computer have CPU, RAM, Storage, Divices(mouse, keyboard ....) as a hardware. And Applications like (Chorme, VScode, Docker....) is a software .
  - Operating System help take mouse and keyboard input, display infomation on the screen and allocate CPU and Memory to do its job 
  - Operating System can interact with and control the hardware as well as interact with Application
  - Manages Resources among Application : If chrome has 70% resources but have'nt use for a while and I open Safari . OS will know and decrese chrome resources then give it to Safari
  - Isolates content Application : So they don't interphere with each other resources 
```

**What are OS task?**
```
  - OS is responsible for allocating and managing the hardware resources like CPU, Memory, Storage and input out devices

  1. Processes Managment
    - What is process ? Process is a small unit that execute on the computer . Like Open VSCode is a process, open chrome is a process
    - Each process has it own isolated space 
    - 1 CPU for 1 process at the time

  2. Memory Managment (RAM)
    - Allocating working Memory
    - Whenever I start Applications that applications need some data so it can work .
    - Can Not execute any Applications without allocating some memory to it
    - RAM limited on hardware
    - When the computer run out the Memory . The OS will handle swapping the Memory .
    - Swapping will slow down the computer
    - What is Memory Swapping ?
      - In this process OS will unload or clear data from RAM and save it into Secondary Memory (Storage) and load the new process data in that clear memory

  3. Storage (Secondary Memory)
    - Persisting data long-term
    - The hard-drive
    - Example I am using VScode and I start writing some code while I am working on that code , that data will load to RAM and being process as I write the code . When I done coding and want to save all data , that data will go to Storage
    - I can store Files, Browser configuration, games, video, picture , etc ...
    - OS handle store in the Structured way . Those data will store and structure in Folder or Directory
    - In Unix systems: tree file system
    - In Window OS : Multiple Root folder

  4. I/O Device
    - OS knows how to handle and translate interactions between apps and devices

  5. Security and Networking
    ----Security----
    - Managing User and Permission. Can have multiple user on 1 computer . Each users have their own password so they can do their own stuff
    - User also have permission : I may have an admin user to allow addminisate and have less privileges user who have less permission so they don't accident break something on OS

    ----Networking----
    - Assigning port and ip address 
```

**How is OS made up ?**
```
  ----Kernel----
  - In the core OS have a Kernal
  - This a part of OS that load first
  - The heart of every OS responsible for managing all the hardward (CPU, RAM, Disk, I/O device)
  - Kernel handle I/O devices using devices driver . Device driver are code or program which allow external devices to interact with computer
  - Kernel is a layer interacting between Application and Hardware . When I start Application it the kernel start the process for that Application, load it into memory and allocate CPU
  - Clean up Resources when App shut down

----Application (Distribution of Linux)----
  - There is Application on top of Kernel like Ubuntu, Debian, Linux Mint
  - Diffent Application layer but base on the same Linux Kernel (different color theme, GUI, color font ....)
  - Android is base on Linux Kernel

----How to interact with Kernel ?----
  - GUI or CLI
  - Which mean can not be accesible or can not be used without the OS user layer
```

# Virtualization and Virtual Machine
```
  ----What is Virtual Machine----
  - With Virtualization is no need separate hardward to install Operating System
  - I can install Window OS on Linux OS , MacOS on Linux OS or vice versa by using Hypervisor

  ----Hypervisor----
  - Hpyervisor is a technology that allow hosting multiple virtual machine on a physical computer on top of OS I have installed

  ----Type1 and Type2 of Hypervisor----
  - Type2 : Guest OS borrow hardward from Host OS
  - Type1 : Instead of install OS on the Host OS . Type1 install directly on the hardward
    - Type1 also call Bare Metal Hypervisor
    - So the Hypervisor control the hardware resources instead of talking to the host OS whether it can borrow resources for its virtual machine . So it sit ontop of hardware and control everything 
```

# Linux File System
```
  - Linux File Systen is hierarchie tree structure
  - 1 root folder and inside root folder I have couple more folder and inside couple more folder I have more Folder .... 
  - 1 Root folder
    |_ /bin
    |_ /sbin
    |_ /usr
      |_ /local
    |_ /etc
    |_ /opt
    |_ /var
    |_ /home

  - Root user has it owns isolated folder seperate from all other users /root

  ----/home----
    - Where all Linux users spaces allocated except Root user . !!! Important to isolated users so I can have multiple Users on my OS that not gonna interfere with each other
    - Each user has it owns space
    - Each user has it owns configuration

  ----There also program that has to be system-wide----

  ----/bin----
    - Stand for binary 
    - /bin folder inside root directory contain the most basic command and binary files command I have available on my OS (cd, ls, cat, echo ....)

  ----/sbin----
    - System binary
    - These command in /sbin is system relevant that these command need a super user permission to execute

  ----/lib----
    - Library Folder
    - Hold the library for those command
    - 1 Program can actually split into different location . Having executable file in /bin and having librarie in /lib

  ----/usr----
    - Stand for user
    - This folder is User location before home Dir was added
    - Inside /usr also have /bin, /lib, /sbin . The same concept as root folder
    - History reason : Bcs of Limitation of Storage , it was split to root binary folder and the rest of them in user folder
    - NOTE: Whenever I execute command in terminal it will execute from /usr/bin (from /usr folder)
    - NOTE: /bin and /sbin has less command then /usr/bin and /usr/sbin

  ----/usr/local----
    - Inside /usr folder I have local folder which also has /bin /lib/ /sbin
    - This is a location where Me as a Linux User are installing myself will actually go
    - Third party applications like VScode, Chrome .... will located here
    - System-wide installation

  ----/opt----
    - Another location where third party or external application will be installed
    - Differnt between /opt and /usr/local is There are some Application do not slpit their code or their file in different directory . This program will install everything in 1 Dir

  ----/boot----
    - For booting the system
    - Should not touch that

  ----/dev----
    - stand for devices
    - Where devices connect to computer will be store (keyboard, mouse etc ....)
    - All files that system need to interact with the device is in /dev

  ----/var----
    - When OS start it will actually logs some data . These logs are in /var
    - /var/cache contain cached data from application programs
    - /var/log contain logs file

  ----/tmp----
    - stand fo tempuraly
    - Store some temp files that process in the background then will be deleted

  - Those folder above is Read-only folder

  ----/etc----
    - Where the system configuration store (network interface configuration, Linux user and password data etc ..., )
```

**Hidden file**
```
  - Begin with dot .
  - To see hidden file : ls -a
  - Hidden file or folder usally automatically generated by OS
  - And hidden applications will automatically create them to store configuration some script they need to execute
  - In addtion to Application themselve generating these folder and files I also have OS itself generating some of these folder and files specificlly for my user
```

# Package Manager 

**What is software package?**
```
  - Software package is a compress archive, contain all required files by a specific software to run
  - Apps usally have dependencies they depend on other software to run 
```

**Package Manager**
```
  - Software package hard to install bcs in Linux 1 Application split among directories
  - That's why we need Package Manager to install software
  - Package Manager Download, Install or Updates existing software from a repository
  - The Package Managet will resolve Dependencies 
```

# Linux Accounts & Groups 

**Linux Accounts**
```
  - 3 Type of Linux Users
    1. Root User : Unrestricted Permission to the whole system
    2. Regular User : This is a user we create to login to the system
    3. Service User : is relevant on Linux Distribution . Bcs Linux wildly use for server and server run different services like DB, Web App ...etc . And each services will have it owns user . Bcs It make sure it isolated in term of permission from each other and ensure better security . And this is a best practice in server managment in Devops . No service should run on root user

  - On 1 machine I may have multiple of those users .
  - I may have multiple Reg User and multiple Service User
```

**Multiple Users on the Server**
```
  - For Linux having multi-server is important for Server
  - Usually server manage by team or administator so multiple people need access to the same server

  ----Why have a User for each team member is important? ?----
  - Someone maybe a senior have more privileges than junior 
  - Bcs we need to know who did what at specific time 
```

**Groups and Permission**
```
  ----How to manage permission on Linux?----

  - I can manage on 2 different level
    1. User Permission : Give User permission directly 
    2. Group Permission :
      - Group user into group
      - Give Permission to the group
```

**User Managment in Practice**
```
  ----Access Control Files----
  - /etc/passwd : Store user account infomation 
  - Example : docker:x:1000:999:,,,:/home/docker:/bin/bash  This line this represent Docker user
    - docker : Name of user
    - x : is encrypted password is stored /etc/shadow file
    - 1000 : is unique id of the user . Root user alway have id of 0
    - 999 : is primary Group id for a user . So group also have ID and each user will have primary group which that user part of
    - /home/docker : User home Dir
    - /bin/bash : User shell

  ----How to add User ?----
    - adduser <username> = Create new user
    - passwd <username> = Change password
    - su - <username> = Login as a username 

    !!! Whenever I create user by default it also create a group with the same name as a user and set that as a primary group id of the user


  ----How to add Groups ?----
    - groupadd <groupname> = create group

    !!! By default system assign the next available GID from the range of group IDs specificed in the login.defs file

  ----How to modify user account ?----
    - usermod [options] <username> = modify user account
    - usermod -g devops tim
      - -g : Make devops a primary group of user tim
      - -G : To add user to multiple secondary group (will overwrite the whole Secondary group list)
      - -aG : Will append a new group to a exsting group
      - devops : is a group
      - tim : username that i want to modify

    ----To Display group----
    - groups = To display groups that user

    ----Create user also add user to secondary group----
    - useradd [OPTIONS] <username> = create new user
    - useradd -G devops nicole
      - useradd : low level command
      - -G : create user with multiple secondary group
      - -d : custome home directory 
```

**Different User and Groups Command**
```
  adduser ---- useradd
  addgroup ---- groupadd
  deluser ---- userdel
  delgroup ---- groupdel

  ----What is the different ?----

  ---adduser and addgroup :---
    - More interactive
    - User friendly
    - Choose conformat UID and GUID values for you
    - Create a home directory with skeletal config automatically
    - Or ask for password in interactive mode

  ---useradd and groupadd :---
    - I need to provide info myself as a parameter
    - Low level command

  ----Which to choose ?----
    - Use useradd groupadd command in script
    - User adduser addgroup command when execute manually
    - The same for other command 
```



















