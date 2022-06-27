<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Table of Contents](#table-of-contents)
- [What&rsquo;s an OS?](#whatrsquos-an-os)
  - [Remote Connection and SSH](#remote-connection-and-ssh)
    - [Remote Connection](#remote-connection)
    - [Secure Shell (SSH)](#secure-shell-ssh)
    - [VPN](#vpn)
  - [Remote Connections on Windows](#remote-connections-on-windows)
    - [PuTTY](#putty)
  - [Components of an Operating System](#components-of-an-operating-system)
    - [Operating System](#operating-system)
  - [Files and File Systems](#files-and-file-systems)
    - [Block Storage](#block-storage)
  - [Process Management](#process-management)
    - [Process](#process)
    - [Program](#program)
    - [Time slice](#time-slice)
    - [Role of Kernel](#role-of-kernel)
  - [Memory Management](#memory-management)
    - [Virtual Memory](#virtual-memory)
    - [Swap Space](#swap-space)
  - [I/O Management](#io-management)
  - [Interacting with the OS: User Space](#interacting-with-the-os-user-space)
  - [Logs](#logs)
  - [The Boot Process](#the-boot-process)
    - [BIOS/UEFI](#biosuefi)
    - [POST](#post)
    - [Boot Device](#boot-device)
    - [Bootloader](#bootloader)
    - [OS](#os)
    - [Kernel](#kernel)
- [Installing an Operating System](#installing-an-operating-system)
  - [Choosing an OS](#choosing-an-os)
  - [Virtual Machines](#virtual-machines)
  - [Installing Windows](#installing-windows)
  - [Installing Linux](#installing-linux)
  - [What is Chrome OS](#what-is-chrome-os)
  - [Installing Mac OS X](#installing-mac-os-x)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


# What&rsquo;s an OS?


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


---

## Remote Connections on Windows


### PuTTY

A free, open source software that you can use to make remote connections through several network protocols, including SSH.

-   PuTTY can be used from CL, as \`putty.exe &#x2013;ssh user@ip<sub>address</sub>\`
-   PuTTY comes with a Plink or PuTTYlink program which can also be used for SSH-ing to other computers.
-   Microsoft provides another way to remotely connect with windows computer via GUI, called Remote Desktop Protocol (RDP).


---

## Components of an Operating System


### Operating System

The whole package that manages our computer&rsquo;s resources and lets us interact with it.

-   Two main parts
-   1) Kernel: Storage and file management, processes, memory control, I/O management
-   2) User Space: Everything out of the scope of the Kernel, like application, CLI tools etc


---

## Files and File Systems

File storage include three things:

1.  Data 2) File handling 3) Meta Data


### Block Storage

Improves faster handling of data because the data isn&rsquo;t stored as one long piece and can be accessed quicker.


---

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


---

## Memory Management


### Virtual Memory

The combination of hard drive space and RAM that acts like memoy that our processes can use.


### Swap Space

Allocated Space for virtual memory.


---

## I/O Management

-   Kernel does Input/Output devices by managing their intercommunicating and resource management etc.


---

## Interacting with the OS: User Space

Two ways to interact with the OS

-   Shell
    
    A program that interprets text commands and sends them to the OS to execute.

-   GUI


---

## Logs

Files that record system events on our computer, just like a system's diary.


---

## The Boot Process

The computer boots in following order.


### BIOS/UEFI

A low-level software that initializes our computer's hardware to make sure everything is good to go.


### POST

Power on Self Test(POST) is performed to make sure computer is in proper working order.


### Boot Device


### Bootloader

A small program that loads the OS.


### OS


### Kernel

-   System Processes
-   User Space


---

# Installing an Operating System


## Choosing an OS


---

## Virtual Machines


---

## Installing Windows


---

## Installing Linux


---

## What is Chrome OS


---

## Installing Mac OS X

