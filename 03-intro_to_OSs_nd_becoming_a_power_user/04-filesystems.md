# Filesystem Types

## Review of Filesystems

- FAT32 reading and writing data to Windows, Linux, and MacOS

  + Shortcomings are, max file size supported is 4 GB

  + Max file system 32 GB

![USB on Linux and Windows](./images/usb.png) 

![USB not Working on Windows](./images/usb_error.png) 
## Disk Anatomy

- A storage device can be divided into partitions

- You can dual-boot Windows and Linux, with disk partitions dedicated for each.

- Other component is Partition table

  + Two main Partition tables are used

    + Master Boot Record (MBR)

    ![MBR](./images/mbr.png) 

    + GUID Partition Table (GPT)

    ![GPT](./images/gpt.png) 

  + For new booting standard UEFI, you need GPT table.

### Partition

The piece of a disk that you can manage.

### Partition Table

Tells the OS how the disk is partitioned.

## Windows: Partitioning and Formatting a Filesystem

- Windows ships with great tool, **Disk Management** Utility.

- To manage disks from CLI, tool called `Diskpart` is used.

### Diskpart

Typing `Diskpart` in the CLI, will open interactive shell.

Next type `list disk` to list out all the storage devices on your computer

Then to select a disk:

```console
select disk <Disk ID>
```

After to wipe all volumes and files from the disk type `clean` in the interactive shell.

To create blank partition in a disk

```console
create partition primary
```

Then, to select the newly created partition

```console
select partition 1
```

To mark it as active, simply type `active`.

To format the disk with filesystem:

```console
format FS=NTFS label=<Label the Disk> quick
```

### Cluster

Cluster (allocation unit size) is the minimum amount of space a file can take up in a volume or drive.

#### Cluster size

Cluster size is the smallest division of storage possible in a drive. Cluster size is important because a file will take up the entire size of the cluster regardless of how much space it actually requires in the cluster.

- For example, if the cluster size is 4kb (the default size for many formats and sizes) and the file you're trying to store is 4.1kb, that file will take up 2 clusters. This means that the drive has effectively lost 3.9 kb of space for use on a single file.

![Cluster size](./images/cluster_size.png) 

### Volume

A single accessible storage area with a single file system; this can be across a single disk or multiple.

### Partition

A logical division of a hard disk that can create unique spaces on a single drive. Generally used for allowing multiple operating systems.

## Windows: Mounting and Unmounting a Filesystem

- When you plug a USB drive, it shows up in the list of your devices, and you can start using it right away.

- When done using, safely eject it.

### Mounting

Making something accessible to the computer, like filesystem or a hard disk.

## Linux: Disk Partitioning and Formatting a Filesystem

- There are different disk partitioning CLI tools
  
  + `parted`: can be used in both interactive and in commandline.

### Parted

To list the devices

```bash
sudo parted -l
```

To run parted in interactive mode on some disk

```bash
sudo parted /dev/sdX
```

You can use help to see different commands used in the interactive mode.

To format the partition with filesystem using `mkfs`

```bash
sudo mkfs -t ext4 /dev/sdXx
```

## Linux: Mounting and Unmounting a Filesystem

To mount the previously formatted disk

```bash
sudo mount /dev/sdXx /my_disk/
```

To unmount the disk

```bash
sudo umount /dev/sdXx
```

### File System table (fstab)

To permanently mount a disk we need to make changes in a `fstab` file.

The `fstab` configuration table consists of six columns containing the following parameters:

  + Device name or UUID (Universally Unique ID)

  + Mount Point: Location for mounting the device

  + Filesystem Type

  + Options : list of mounting options in use, delimited by commas.

  + Backup operation of dump - this is an outdated method for making device or partition backups and command dumps. It should not be used. In the past, this column contained a binary code that signified:

    + 0 = turns off backups

    + 1 = turns on backups

  + Filesystem check (fsck) order or Pass - The order in which the mounted device should be checked by the `fsck` utility:

    + 0 = `fsck` should not run a check on the filesystem

    + 1 = mounted device is the root file system and should be checked by the `fsck` command first.

    + 2 = mounted device is a disk partition, which should be checked by `fsck` command after the root file system.

Example of an `fstab` table:

![FSTAB](./images/fstab.png) 

To get a UUID of a disk

```bash
sudo blkid
```

![Fstab Options](./images/fstab_options.png) 


## Windows: Swap

- Windows use **Memory Manager** to handle virtual memory.

- In Windows, pages saved to disk are stored in a special hidden file on the root partition of a volume called **pagefile.sys**

- Windows provides to way to modify size, number and location of paging files through a control panel applet called **System Properties**.

### Virtual memory

How our OS provides the physical memory available in our computer (like RAM) to the applications that run on the computer.

## Linux: Swap

- You can make swap, with tools like `fdisk`, `parted`, `gparted` etc.

- To make it auto-mount on system start, add its entry in the `fstab` file.

### Swap space

In Linux, the dedicated area of the hard drive used for virtual memory.

## Windows: Files

- NTFS uses **Master File Table or MFT** to represent the files.

- Every file on the system has at least one entry on the MFT

- Shortcut is an MFT entry which takes us to the specific location of a file, which it is a shortcut of.

- Other methods to link to files are:

  + Symbolic Links: OS treats Symbolic links just like the files themselves

To create a symbolic link:

```powershell
mklink <Symlink Name> <Original File Name> 
```

  + Hard Links: When you create a hard link in NTFS, an entry is added to the MFT that points to the linked file record number, not the name of the file. This means the file name of the target can change and the hard link will still point to it

To create a hard link:

```powershell
mklink /H <Hard link Name> <Original File Name>
```

![Master File Table](./images/mft.png) 

### File metadata

All the data, other than the file contents.
