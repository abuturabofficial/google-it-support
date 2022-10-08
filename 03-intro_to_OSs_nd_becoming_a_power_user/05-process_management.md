<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Life of a process](#life-of-a-process)
  - [Program vs Process Revisited](#program-vs-process-revisited)
    - [Programs](#programs)
    - [Processes](#processes)
  - [Windows: Process Creation and Termination](#windows-process-creation-and-termination)
  - [Linux: Process Creation and Termination](#linux-process-creation-and-termination)
    - [INIT Process](#init-process)
- [Managing Processes](#managing-processes)
  - [Windows: Reading Process Information](#windows-reading-process-information)
  - [Linux: Reading Process Information](#linux-reading-process-information)
  - [Windows: Signals](#windows-signals)
    - [Signal](#signal)
  - [Linux: Signals](#linux-signals)
  - [Windows: Managing Processes](#windows-managing-processes)
    - [Process Explorer](#process-explorer)
  - [Linux: Managing Processes](#linux-managing-processes)
- [Process Utilization](#process-utilization)
  - [Windows: Resource Monitoring](#windows-resource-monitoring)
  - [Linux: Resource Monitoring](#linux-resource-monitoring)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Life of a process

## Program vs Process Revisited

### Programs

The applications that we can run, like the Chrome web browser.

### Processes

Programs that are running.

- When you open a program, a process is started, and it gets the **process ID or PID**.

- **Background or Daemon Processes** are those who are always running in the background.

## Windows: Process Creation and Termination

- When Windows boots up or starts, the first non-kernel user mode that starts is the **Session Manager Subsystem or smss.exe**.

  + It kicks start some processes before login

  + Then `smss.exe` starts `winlogon.exe` along with **client/server runtime subsystem** or **csrss.exe**, which handles GUI and CLI.

  + Unlike Linux, Windows' processes can run own their own in their respective **Environment** created by **smss.exe** independent of their parent process.

- To terminate a process from CLI, `taskkill` utility is used, which can find and halt a process.

  + `taskkill` uses PID to identify the process running.

To kill notepad with `taskkill` from CLI:

```console
taskkill /pid 5856
```

To forcefully kill a rogue process:

```console
taskkill /F /PID <PID>
```

## Linux: Process Creation and Termination

- In Linux, process has parent child relationship.

- So every process that runs on the system has some parent process.

- `init` is the parent process for the kernel

### INIT Process

When you start up your computer, the kernel creates a process called **init**, which has a **PID of 1**.

# Managing Processes

## Windows: Reading Process Information

- **Task Manager or taskmgr.exe** is one way of obtaining processes information on Windows.

To show all running processes in CLI:

```console
tasklist
```

The PowerShell command for the same:

```powershell
Get-Process
```

## Linux: Reading Process Information

To see process running on Linux:

```bash
ps -x
```

The following **STAT** for `ps -x` command are used to show processes current status

  + R: running

  + T: stopped

  + S interruptible sleep

To see full list of running processes even by other users run:

```bash
ps -ef #'f' for full
```

  + UID: User ID

  + PID: Process ID

  + PPID: Parent Process ID

  + C: Number of children processes

  + STIME: Start Time of Process

  + TTY: Terminal associated with the process

  + TIME: Total CPU time process is taking up

  + CMD: Name of the command running

Everything in a Linux is a file, even the processes. So we can view them in `/proc`

```bash
ls -l /proc
```

## Windows: Signals

- If we want to close unresponsive process, we use signals.

- The most common is **SIGINT** or signal interrupt. You can send this signal to a running process with the **CTRL+C** key combination.

![Windows Signals](./images/sig.png) 

### Signal

A way to tell a process that something's just happened.

## Linux: Signals

There are lots of signals in Linux, starting with **SIG**. I.e. **SIGTERM**, SIGINT** etc.

## Windows: Managing Processes

- To restart or pause a process and to do even much more, **Process Explorer** tool is used.

### Process Explorer

A utility, Microsoft created to let IT Support Specialists, system admins and other users to look at running processes.

## Linux: Managing Processes

- To terminate a process, `kill` command is used.

  + `kill` without any parameters, sends `SIGINT` signal to the program/process to clean is running processes and close them properly

To kill a process

```bash
kill <PID>
```

To send **SIGKILL** via `kill` command:

```bash
kill -KILL <PID>
```

`-KILL` should the lost resort to stop a process, it doesn't give time to the process for cleanup, it may cause more harm than good.

To put process on pause instead of killing, **SIGSTP** or signal stop, is used 

```bash
kill -TSTP <PID>
```

To resume from suspend:

```bash
kill -CONT <PID>
```

# Process Utilization

## Windows: Resource Monitoring

- **Resource Monitoring tool** is used.

- To get resource monitoring from CLI

```powershell
Get-Process
```

To get the three most resource heavy processes:

```powershell
Get-Process | Sort CPU -descending | Select -first 3 -Property ID,ProcessName,CPU
```

## Linux: Resource Monitoring

`top` is a useful resource monitoring CLI tool:

```bash
top
```

Another useful CLI tool is `uptime`, which show info about the current time, how long your computer running, how many users are logged on, and what the load average of your machine is.

When ejecting USB drive, you get error "Device or resource busy" though none of the files on the USB drive is in use or opened anywhere, or so you think. Using the `lsof` lists open files and what processes are using them.

  + It is great for tracking down pesky processes that are holding open files.
