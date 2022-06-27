
# Table of Contents

1.  [What&rsquo;s an OS?](#org89141af)
    1.  [Remote Connection and SSH](#org8bf0007)
    2.  [Remote Connections on Windows](#orga5dd78f)
    3.  [Components of an Operating System](#org78e325d)
    4.  [Files and File Systems](#org3ca9219)
    5.  [Process Management](#orgf34ebc9)
    6.  [Memory Management](#org3a1cf38)
    7.  [I/O Management](#org0e22ebd)
    8.  [Interacting with the OS: User Space](#orga4369bf)
    9.  [Logs](#org996f05f)
    10. [The Boot Process](#orgdfe5210)
2.  [Installing an Operating System](#org210380a)
    1.  [Choosing an OS](#orgd3dcccb)
    2.  [Virtual Machines](#org4c2ef59)
    3.  [Installing Windows](#orgd184441)
    4.  [Installing Linux](#orgde4fe65)
    5.  [What is Chrome OS](#org87c728e)
    6.  [Installing Mac OS X](#orgbfcb80e)



<a id="org89141af"></a>

# What&rsquo;s an OS?


<a id="org8bf0007"></a>

## Remote Connection and SSH


### Remote Connection

Allows us to manage multiple machines from anywhere in the world.


### Secure Shell (SSH)

A protocol implemented by other programs to securely access one computer from another.

-   Popular software to work with SSH, on Linux, OpenSSH program, while on Windows , PuTTY is used.
-   In SSH, a pair of public and private keys is used to authenticate the process.
-   To securely connect to a remote machine, a VPN is used.


### VPN

Allows you to connect to a private network, like your work network, over the Internet.


<a id="orga5dd78f"></a>

## Remote Connections on Windows


### PuTTY

A free, open source software that you can use to make remote connections through several network protocols, including SSH.

-   PuTTY can be used from CL, as \`putty.exe &#x2013;ssh user@ip<sub>address</sub>\`
-   PuTTY comes with a Plink or PuTTYlink program which can also be used for SSH-ing to other computers.
-   Microsoft provides another way to remotely connect with windows computer via GUI, called Remote Desktop Protocol (RDP).


<a id="org78e325d"></a>

## Components of an Operating System


### Operating System

The whole package that manages our computer&rsquo;s resources and lets us interact with it.

-   Two main parts
-   1) Kernel: Storage and file management, processes, memory control, I/O management
-   2) User Space: Everything out of the scope of the Kernel, like application, CLI tools etc


<a id="org3ca9219"></a>

## Files and File Systems

File storage include three things:

1.  Data 2) File handling 3) Meta Data


### Block Storage

Improves faster handling of data because the data isn&rsquo;t stored as one long piece and can be accessed quicker.


<a id="orgf34ebc9"></a>

## Process Management


### Process

A program that&rsquo;s executing, like our internet browser or text editor.


### Program

An application that we can run, like Chrome.


### Time slice

A very short interval of time, that gets allocated to a process for CPU execution.


### Role of Kernel

-   Create processes
-   efficiently schedules them
-   Manages how processes are terminated


<a id="org3a1cf38"></a>

## Memory Management


### Virtual Memory

The combination of hard drive space and RAM that acts like memoy that our processes can use.


### Swap Space

Allocated Space for virtual memory.


<a id="org0e22ebd"></a>

## I/O Management

-   Kernel does Input/Output devices by managing their intercommunicating and resource management etc.


<a id="orga4369bf"></a>

## Interacting with the OS: User Space

Two ways to interact with the OS

-   Shell
    
    A program that interprets text commands and sends them to the OS to execute.

-   GUI


<a id="org996f05f"></a>

## Logs

Files that record system events on our computer, just like a system&rsquo;s diary.


<a id="orgdfe5210"></a>

## The Boot Process

The computer boots in following order.


### BIOS/UEFI

A low-level software that initializes our computer&rsquo;s hardware to make sure everything is good to go.


### POST

Power on Self Test(POST) is performed to make sure computer is in proper working order.


### Boot Device


### Bootloader

A small program that loads the OS.


### OS


### Kernel

-   System Processes
-   User Space


<a id="org210380a"></a>

# Installing an Operating System


<a id="orgd3dcccb"></a>

## Choosing an OS


<a id="org4c2ef59"></a>

## Virtual Machines


<a id="orgd184441"></a>

## Installing Windows


<a id="orgde4fe65"></a>

## Installing Linux


<a id="org87c728e"></a>

## What is Chrome OS


<a id="orgbfcb80e"></a>

## Installing Mac OS X

