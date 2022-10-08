<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Software Distribution](#software-distribution)
  - [Windows: Software Packages](#windows-software-packages)
    - [Executable file (.exe)](#executable-file-exe)
    - [Microsoft install package (.msi)](#microsoft-install-package-msi)
  - [Linux: Software Packages](#linux-software-packages)
  - [Mobile App Packages](#mobile-app-packages)
    - [App Stores](#app-stores)
    - [Side-loading](#side-loading)
  - [Windows: Archives](#windows-archives)
    - [Archive](#archive)
    - [Package archives](#package-archives)
  - [Linux: Archives](#linux-archives)
  - [Windows: Package Dependencies](#windows-package-dependencies)
    - [Having Dependencies](#having-dependencies)
    - [Library](#library)
    - [cmdlet](#cmdlet)
  - [Linux: Package Dependencies](#linux-package-dependencies)
    - [Package managers](#package-managers)
- [Package Managers](#package-managers)
  - [Windows: Package Manager](#windows-package-manager)
  - [Linux: Package Manager Apt](#linux-package-manager-apt)
    - [Personal Package Archive (PPA)](#personal-package-archive-ppa)
- [What's happening in the background?](#whats-happening-in-the-background)
  - [Windows: Underneath the Hood](#windows-underneath-the-hood)
  - [Linux: Underneath the Hood](#linux-underneath-the-hood)
- [Device Software Management](#device-software-management)
  - [Windows: Devices and Drivers](#windows-devices-and-drivers)
    - [Driver](#driver)
  - [Linux: Devices and Drivers](#linux-devices-and-drivers)
    - [Character Devices](#character-devices)
    - [Block Devices](#block-devices)
    - [Pseudo Devices](#pseudo-devices)
  - [Windows: Operating System Updates](#windows-operating-system-updates)
    - [Security Patch](#security-patch)
  - [Linux: Operating System Updates](#linux-operating-system-updates)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Software Distribution

## Windows: Software Packages

- In Windows, software is usually packaged in a **.exe** executable file.

- Software is packaged according Microsoft **Portable Executable** or **PE** format.

- Executable not only include install instructions but also things like text or computer code, images that the program might use, and potentially something called an **MSI** file.

- For precise granular control over installation, you can use executable with a custom installer packaged in something like **setup.exe**.

- On the other hand, **.msi** installer along with Windows installer program has some strict guidelines to be followed.

- Windows Store uses a package format called **APPX**.

- To install an executable from CLI, type its name.

### Executable file (.exe)

Contain instructions for a computer to execute when they're run.

### Microsoft install package (.msi)

Used to guide a program called the Windows Installer in the installation, maintenance, and removal of programs on the Windows operating system.

## Linux: Software Packages

- Fedora use **Red-Hat package manager package or (.RPM)**.

- Debian uses **.deb** file.

- To install a standalone .deb package

```bash
sudo dpkg -i abc.deb
```

- To remove package on Debian

```bash
sudo dpkg -r abc.deb
```

- To list .deb Packages

```bash
dpkg -l
```

## Mobile App Packages

- Software is distributed as Mobile Applications or Apps.

- Mobile phones use App stores for software installation

- Enterprise App management allows companies to distribute their custom apps internally.

  + Enterprise Apps are managed through **Mobile Device Management or (MDM)** service.

- Another way to install apps is through side-loading

- Apps stored their files to storage assigned to them called **cache**.

  + Clearing the cache will remove all changes to the settings, and sign out of any accounts that the app was signed-into.

  + Clearing the cache might not be the first step in application troubleshooting, but it is handy in desperate times.

### App Stores

A central, managed marketplace for app developers to publish and sell mobile apps.

### Side-loading

Where you install mobile apps directly, without using an app store.

- Mobile apps are standalone software Packages, so they contain all their dependencies.

- To compress files from CLI

```powershell
Compress-Archive -Path <filepath: files to be compressed> <filepath: Where to save compressed file>
```

## Windows: Archives

- 7-zip is a popular Windows tools for archives management.

### Archive

Comprised of one or more files that's compressed into a single file.

- Popular archive types are **.tar, .zip, .rar**.

### Package archives

The core or source software files that are compressed into one file.

## Linux: Archives

- p7zip is Linux version of 7-zip.

  + To extract a file, use the command `7z` and the flag **e** for extract and then the file you want to extract.

```bash
7z e <filepath>
```

## Windows: Package Dependencies

- A game might depend on rendering library for graphic and physics engine for correct movements.

- In Windows, these shared libraries are called **Dynamic Link Libraries or DLL**.
  
  + A useful feature of DLL is, one DLL can be used by 'many' different programs.

- In the past, when one DLL gets updated, some programs dependent on it, would become unusable, as they didn't know how update DLL for next version number. 

- On modern systems, more shared libraries and resources in Windows are managed by something called **side-by-side assemblies or SxS**

  + Most of these shared libraries are stored in `C:\Windows\WinSxS`

  + If an application needs to use a shared library, this is declared in file called **manifest**.

  + SxS stores multiple versions of DLLs, so programs dependent on them remain functioning.

  + Using a **cmdlet** `Find-Package`, can locate software, along with its dependencies right from the command line.

### Having Dependencies

Counting on other pieces of software to make an application work, since one bit of code depends on another, in order to work.

### Library

A way to package a bunch of useful code that someone else wrote.

### cmdlet

A name given to Windows PowerShell commands

## Linux: Package Dependencies

- **dpkg** in Debian and Debian-based Linux systems doesn't handle dependencies automatically

- So, package managers come to your rescue for automatic dependency resolution.

### Package managers

Come with the works to make package installation and removal easier, including installing package dependencies.

# Package Managers

## Windows: Package Manager

"Makes sure that the process of software installation, removal, update, and dependency management is as easy and automatic as possible."

- Chocolatey is third party package manager for Windows.

- NuGet is another third party package manager for Windows.

  + Based on Windows PowerShell

  + Configuration management tools like **SCCM & puppet** integrate with Chocolatey.

- To add Chocolatey as a package source

```powershell
Register-PackageSource -Name chocolatey -ProvideName Chocolatey -Location https://chocolatey.org/api/v2
```

To verify package source

```powershell
Get-PackageSource
```

To find a package

```powershell
Find-Package sysinternals -IncludeDependencies
```

To actually install this package

```powershell
Install-Package -Name sysinternals
```

To verify installation

```powershell
Get-Package -name sysinternals
```

To uninstall a package

```powershell
Uninstall-Package -Name sysinternals
```

## Linux: Package Manager Apt

- apt or Advanced Package Tool

- Ubuntu and Ubuntu based distros use apt.

- APT comes with default distro software repo linked.

- To add other repos, we add them through `/etc/apt/sources.list`

- Ubuntu and based-distros have additional repos in the form of **PPAs**

  + PPAs are not as vetted by distros, so use them carefully or you might get infected, or break your installation with defected programs.

### Personal Package Archive (PPA)

A Personal Package Archive or PPA is a software repo for uploading source packages to be built and published as an **Advanced Packaging Tool (APT)** repo by Launchpad.

# What's happening in the background?

## Windows: Underneath the Hood

- When click an .exe to install, next step depends on the developer, how he, setups the installation instructions for his/her program.

- If an EXE contains code for a custom installation that doesn't use the Windows installer system, then the details of what happens under the hood will be mostly unclear. As the most Windows' software are closed source packages.

- So, you can't really see what instructions are given, but tools like **Process Monitoring** provided by Microsoft CIS internal toolkit.

  + It will show any activity the installation executable is taking, like the files it writes and any process activity it performs.

- In case MSI files, though code is closed source, but developers need to stick to strict guidelines.

  + **Orca** tool lets you examine, create and edit MSI files, it's part of Windows SDK.

## Linux: Underneath the Hood

- Installations are clearer than Windows due to open nature of the OS

- Software usually consists of setup script, actual app files and README.

- Most devices you've got on you computer will be groped together according to some broad categories by Windows.

- This grouping usually happens automatically when you plug in a new device, **Plug&Play or PnP** system.

- When new device plugs-in, Windows asks for its hardware ID.

- When it gets right hardware ID, it searches for its drivers in some known locations, starting with a local list of well-known drivers. Then goes on to Windows Update or the driver store.

- Other times devices comes with custom drivers.

# Device Software Management

## Windows: Devices and Drivers

- **Device Manager** console is used in GUI, for devices and drivers management.

- You can open it by searching **devmgmt.msc** from the search console, or right-click on **This PC** and click **Device Manager**.

### Driver

Used to help our hardware devices interact with our OS.

## Linux: Devices and Drivers

- In Linux, everything is considered a file, even the hardware devices.

- When a new device is connected, a file is created in the `/dev/` directory.

- There are lots of devices in `/dev/` directory, but not all of them are physical devices.

- The more common one in there are **character devices** and **block devices**.

- As in long `ls` listing `-` in the front represents file, and `d` represents `directory`, in `/dev/`, `c` shows block devices, and `b` represents block devices.

- Device drivers in Linux are easy at the same time difficult to install.

  + Linux kernel is monolithic software, that contains drivers for popular devices as well.

  + The devices that don't have driver backed in the kernel, will have drivers in the form of **kernel modules**.

### Character Devices

Like a keyboard or a mouse, transmit data character by character.

### Block Devices

Like USB drives, hard drives and CDROMs, transfer blocks of data; a data block is just a unit of data storage.

### Pseudo Devices

Device nodes on Unix-like OSs, that don't necessarily have to correspond to physical devices. I.e. `/dev/null`, `/dev/zero`, `/dev/full` etc.

## Windows: Operating System Updates

- When your OS vendor discover security hole in a system, they prepare a security patch.

- As an IT specialist, it's important keep your system up-to-date with security and other patches, though feature updates can be delayed for reasons.

- The Windows Update Client service runs in the background and download and install security patches and updates.

### Security Patch

Software that's meant to fix up a security hole.

## Linux: Operating System Updates

- For Ubuntu based distros

```bash
sudo apt update && sudo apt upgrade
```

- To be on latest security patches, you need to run and update newer kernels.

To see your kernel version

```bash
uname -r
```

`-r` is a flag, to know kernel release, to know kernel version you have.
