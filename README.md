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
    - For Security : Managing User and Permission. Can have multiple user on 1 computer 







```
