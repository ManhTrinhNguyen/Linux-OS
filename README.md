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

    ----Remove user from a Group----
    - gpasswd -d <username> <groupname>
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

# File Ownership & Permission

**Ownership**
```
  - Everything in Linux is a file
  - Ownership is mean who own the file
  - Each file have 2 different owner : User and Group
    - User : is usally who created the file
    - Group : Primary group of that user
  - Owner of the file is someone who has any permission or any access permission to that file 

  - chown <username>:<groupname> <filename> = change ownership of the file
  - chgroup <groupname> <filename> = change only group of the file
```

**Permission**

<img width="720" alt="Screenshot 2025-02-06 at 13 42 10" src="https://github.com/user-attachments/assets/8b53509f-53c0-4bc5-b273-32684ab49e2b" />

```
  ----First column (File Type)----
  -d stand for directory
  - stand for regular file
  l stand for symbol link
  c stand for character device file

  Then Permission will divide into next 3 parts (3 columns for 1 part)
 
  - Part 1 will belong to Owner
  - Part 2 will belong to Groups
  - Part 3 will belong to Others

  - rwx stand for Read Write Execute | - stand for no permission 
```

**Modifying Permission**

<img width="1072" alt="Screenshot 2025-02-06 at 13 56 12" src="https://github.com/user-attachments/assets/f8b03efb-c12a-485c-b93e-4f45b6d721f7" />

```
  ----First way----
  chmod -x <filename> = take away execute permission of all owners
  chmod g+x <filename> = add execute permission on group owner

  ----Second way----
  u stand for user
  g stand for group
  o stand for other

  chmod u=rwx <filename> = add read write execute permission in user owner 
```

# Environment Variable 

**What is Environment Variable ?**
```
  - Each user has its own Environment where it works and execute stuff
  - Each user can configure its own environment/account by setting preferences
  - These OS configurations should be isolated from other user environment 
```

**Where does OS store and keep track all user Environment?**
```
  - OS store these info in the Environment Variable
  - Which basically pieces of infomation defined by Key-Value pairs
  - These ENV are available for the whole entire environment not just for one specific script

  ----How to access ENV ?----
  - printenv  : will show me all ENV
  - printenv <KEY> : will show me specific ENV

  - ENV can also be used by Linux Program or commands by referencing them with : $<variable-name>
```

**Application ENV Variable**
```
  ----Use case----
  - OS store infomation about the environment
  - Create our own ENV in addition to what OS provided
  - To store Authentication or Secret Token or some Sentitive so not everybody can connect to it as a ENV
  - By creating these env vars we make them Available in the environment
  - All apps and processes can now access these as ENV

  - Also make Application flexible 
```

**How to create ENV**
```
  export DB_USERNAME=username : This way is not permamnent
  
  ----To persisting ENV user-specific----
  - There is a file in each user home directory : .bashrc
  - .bashrc Created or automate-generated by for the shell program that My user using that by default
  - After add ENV in .bashrc I need to reload system : source .bashrc 

  ----Shell specific configuration file----
  - Per-user shell specific configuration files
  - Variable set in this file .bashrc or .zshrc are loaded whenever a bash or zsh login is entered

  ----To persisting ENV system-wide----
  - System wild Environment : /etc/environment
  - In the /etc/environment has 1 environment variable called PATH. This is a globally said ENV it has the same value for all user in the system
  - What is PATH ? . Path is list of directories with executable or binary file in there . Each directory separate by :
  - The way it work is Whenever I execute a command or program the system check all of PATH var location to find that command or program binary file and execute it from there . That mean whenever we install software like python , java, nodejs or etc.... the binary file will get added into one of those location and that is why we are able to execute command on CLI
  - So whenever we installed executable program and provide Path variable with the location we can run command to execute the program

  ----How to add custom command or program by useing $PATH----
  - We can add the location to the PATH only for our user :
    - In .bashrc : add PATH=$PATH:<location of the excutable file>
      - $PATH: get all Refernces PATH of all user from the system
      - :<location> : append to location I want to execute

    - Purpose of PATH is instead of me having to provide the full the absolute location . I just need to provide the specific location in wherever in the file 
```
**Networking**

**LAN**
```
  - LAN : Local Area Network

  - LAN is a network of a bunch of devices connected together in 1 physical location

  - This could be as small as house LAN, LAN of huge office building or school campus with alot of Devices

  - Each devices is identify by a unique IP address

  - Devices communicate to each other using IP address

  - For example if my computer want to send something to a Printer to print . It must know Printer's IP address and send the information there  
```

**IP Address**

<img width="400" alt="Screenshot 2025-02-26 at 18 32 58" src="https://github.com/user-attachments/assets/c53a0679-be5c-4edf-aadc-f18bb4641f8b" />

```
  - IP address is a 32 bit values .

  - IP address or IPv4 address is composed of 32 bits

  - Every 8 bits are group into an Octet and each Octer can be represented as a decimal number that human can read

  - Octet with all Eight Zero is 0 (in decimal) . Octet with all Eight One is 255 (in decimal) -> That mean IP Address can range from 0.0.0.0 to 255.255.255.255
```

**How do devices know each othet IP address | How can they send thing to each other ?**

**Switch**
```
  - That is the task of special device on a LAN called Switch

  - Switch sit within a LAN and know all IP Address of all devices and therefor help them communicate with each other

  - So all the devices can talk to each other in a LAN using Swtich . But how do they talk to a outside LAN ? like a Server 
```

**Router**

<img width="500" alt="Screenshot 2025-02-26 at 18 46 13" src="https://github.com/user-attachments/assets/abdc0c73-9fd0-4c71-a16f-76fc94e33d25" />

```
  - For connecting to outside devices there is a special device called Router

  - Router is a network device that sit between LAN and WAN (Wide Area Network)

  - So Router connect devices on local area network and wide area network

  - Which mean the Router connect me to the Internet

  - For example I want to Open FB apps in my Phone . I send the request through a Router then Router will send the request to Facebook server over the Internent and the IP address of a Router called Gateway

  - Network Gateway = Router
```

**Subnet**
```
  - Now other question is when a devices in LAN send a request to other devices . How does it know that device in the LAN or WAN ?

  - So they will decide on the IP Address of a Target Device

  - Every devices have a unique IP address. These IP address are not random

  - They are all belong to the same range of IP addresses to identifies devices in the same network and that IP address range called Subnet or Sub-network
```

**Subnet Example**

<img width="400" alt="Screenshot 2025-02-26 at 18 53 09" src="https://github.com/user-attachments/assets/c30d3ec9-7d57-4be3-8b8f-77d7f1b8c311" />


First part is a IP address , and that is a starting point of that IP Address range (First IP address in the Range)

Second part is called Subnet Mask (Set the IP Range) and it define that whatever IP address of devices start with 192.168.0.x it will belong to a LAN

If I change the Subnet Mask value from 255.255.255.0 to 255.255.0.0 and this will define an IP Address Range start with 192.168.0.x to 192.168.x.x . So all the IP address start with 192.168.x.x with belong the same LAN

`255.255.0.0` mean that 16 bits are fixed 

`255.255.255.0` mean that 24 bits are fixed 

#### CIDR Block 

Subnet Mask dictates how many bits are fixed . Base this logic there is a short hand way of writing this called CIDR Block

  - Written like this `192.168.0.0/16` or `192.168.0.0/24`

#### Recap 

<img width="600" alt="Screenshot 2025-04-11 at 13 53 09" src="https://github.com/user-attachments/assets/395097d7-0252-40df-b805-ec9e8fcebfb7" />

We have a range of IP addresses that are available in a LAN . Every device in that local area network will get an IP Address from that range . 

When We send a Request to an IP address within our LAN, the request will go to the Switch and it will forwarded to the device within a LAN 

In the IP Address is external it will go to the internet through the Router . 

That mean any device needs 3 pieces of data for communication : IP Address, Subnet, Gateway

#### Network Address Translation (NAT)

Internally in a LAN, we have an IP Address range that a network administrator of the company, or school, or in case of my own house, my Internet Provider chooses . And that each device will get a unique IP Address from that range . And suppose the device in our LAN is talking to a device in another LAN . How do we make sure not every network administrator selects the same range and the IP address in our LAN don't overlap or aren't the same as someone else's LAN ?

They way it work is that the IP Addresses of devices that belong to a LAN are not visible to outside network or internet 

So When I send a request to FB from my Laptop my Laptop IP Address from the LAN range does not arrive at FB Server instead it is replaced by the IP Address of the router, and this functionality of the router called a Network Address Translation or NAT . 

  - Laptop send request - It go to a router -> Router will then request that on the devices behalf from internet and the response will then be sent back to the device

**This is Important Concept and have 2 main Advantage**

- Security and Protection of devices within LAN bcs my IP Address doesn't directly expose

- Reuse IP address ranges multiple times without conflicting with each other

- So 2 Company can have the same IP Address range within their own local area network . And they will not know about each other . So there will be no conflict . This is so efficent bcs there are a limited number of IP Addresses I get from IPV4 address range .

 















