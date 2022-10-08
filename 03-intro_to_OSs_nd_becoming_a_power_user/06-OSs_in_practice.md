<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Remote Access](#remote-access)
  - [Remote Connection and SSH](#remote-connection-and-ssh)
    - [Remote Connection](#remote-connection)
    - [Secure shell (SSH)](#secure-shell-ssh)
    - [Virtual private network (VPN)](#virtual-private-network-vpn)
  - [Remote Connections on Windows](#remote-connections-on-windows)
    - [PuTTY](#putty)
  - [Remote Connection File Transfer](#remote-connection-file-transfer)
    - [Secure copy (SCP)](#secure-copy-scp)
  - [Remote Connection File Transfer on Windows](#remote-connection-file-transfer-on-windows)
- [Virtualization](#virtualization)
  - [Virtual Machines](#virtual-machines)
    - [Virtual Instance](#virtual-instance)
- [Logging](#logging)
  - [System Monitoring](#system-monitoring)
    - [Log](#log)
    - [Logging](#logging-1)
  - [The Windows Event Viewer](#the-windows-event-viewer)
  - [Linux logs](#linux-logs)
  - [Working with Logs](#working-with-logs)
- [Operating System Deployment](#operating-system-deployment)
  - [Imaging Software](#imaging-software)
  - [Operating Systems Deployment Methods](#operating-systems-deployment-methods)
  - [Mobile Device Resetting and Imaging](#mobile-device-resetting-and-imaging)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Remote Access

## Remote Connection and SSH

- Most popular SSH client on Linux is **OpenSSH program.

- Most popular SSH program on Windows is **PuTTY**.

- Another way to connect to a remote machine is **VPN**.

- In Linux, GUI remote connection can be established through programs like **RealVNC**.

- On MAC, remote GUI connections are possible via **Microsoft RDP on Mac**.

### Remote Connection

Allows us to manage multiple machines from anywhere in the world.

### Secure shell (SSH)

A protocol implemented by other programs to securely access one computer from another.

- We can authenticate via password in SSH.

- But more secure way is the use of SSH keys. An SSH key is a pair of two keys:

  + Private

  + Public

### Virtual private network (VPN)

Allows you to connect to a private network like your work network, over the Internet.

## Remote Connections on Windows

- Microsoft has built **Remote Desktop Protocol or RDP** for GUI remote connections.

  + A client named **Microsoft Terminal Services Client or mtsc.exe** is used for remote RDP connections.

### PuTTY

A free, open source software that you can use to make remote connections through several network protocols, including SSH.

To connect via PuTTY in a CLI:

```powershell
putty.exe -ssh username@ip_address <Port Number> # Port number is 22 by default for SSH connections
```

To enable remote connection on a pc go-to:

```
MY PC > Properties > Remote Settings
```

## Remote Connection File Transfer

### Secure copy (SCP)

A command you can use in Linux to copy files between computers on a network.

To copy file from local computer to remote:

```bash
scp <filepath> username@ip_address:location
```

## Remote Connection File Transfer on Windows

- PuTTY comes with **PuTTY Secure Copy Client or pscp.exe**.

```powershell
pscp.exe <filepath> username@ip_address:location
```

- To transfer files via PuTTY is little time consuming, so Windows came up with the concept of **ShareFolders**.

To share folders via CLI:

```console
net share <ShareName>=<drive>:<DirectoryPath> /grant:everyone,full
```

To list currently shared folders on your computer:

```console
net share
```

# Virtualization

## Virtual Machines

- To manage virtual instances we can use FOSS program **Virtual Box**.

### Virtual Instance

A single virtual machine.

# Logging

## System Monitoring

### Log

A log is a system diary of events happening on the system.

### Logging

The act of creating log events.

## The Windows Event Viewer

It stores all the events happening on a Windows computer.

## Linux logs

- The logs in Linux are stored in `/var/log` directory.

- One log file that pretty much everything on the system is `/var/log/syslog`

- The utility **logrotate** is used for log cleanup by the system.

- **Centralized logging** is used for parsing multiple systems log files in a single place.

## Working with Logs

The logs are written in very standard way, so we don't need to go through each and every bit of them to troubleshoot problems, all you need to do is look for specific things.

  + Logs can be searched with keywords like, **error**.

  + Name of the troublesome program.

  + The troubleshooting technique is viewing logs in the real time, to find the out the specific errors causing the program to fail.

To see real-time logs in Linux:

```bash
tail -f /var/log/syslog
```

# Operating System Deployment

## Imaging Software

- It is extremely cumbersome to install OSs on new machines via USB drive formatted with OS.

- In IT world, tools are used to format a machine with an image of another machine, which includes everything, from the OS to the settings.

## Operating Systems Deployment Methods

- Disk cloning tools are used to obtain an image of a computer OS and settings. Some tools are:

  + Clonezilla (FOSS)

  + Symantec Ghost (Commercial)

- Different disk cloning tools offer different methods to clone systems

  + Disk-to-disk cloning

Lets use Linux CLI tool `dd` to copy files from a disk to make a clone.

To copy from USB drive, first unmount it:

```bash
sudo umount /dev/sdX
```

Then run `dd`:

```bash
sudo dd if=/dev/sdX of=~/Desktop/my_usb_image.img bs=100M
```

## Mobile Device Resetting and Imaging

- Factory resetting a device clean all user data and apps, and return the device to its original factory condition.

  + Watch out for expansion storages, like SD cards, as factory reset may format them too.

  + You will require primary account credentials to factory reset, this prevents misuse of stolen devices.

- Re-flash a factory software can be done through computer.
