
# Table of Contents

1.  [The Modern Computer](#org63edb25)
    1.  [Introduction to Computer Hardware](#org8a8a4f3)
    2.  [Programs and Hardware](#orgcab7fb9)
2.  [Components](#org39f1e58)
    1.  [CPU](#orgf521a88)
    2.  [RAM](#org15fe6ee)
    3.  [Motherboards](#orgd6e5274)
    4.  [Storage](#org4f8e445)
    5.  [Power Supplies](#orgc161a71)
    6.  [Mobile Devices](#orgd4957d3)
    7.  [Batteries and Charging Systems](#orgcd6b949)
    8.  [Peripherals](#org699270d)
    9.  [Projector](#org04fe501)
3.  [Starting it Up](#org6b57928)
    1.  [Bios](#orgfe49be7)
    2.  [Putting all together](#org3d5210e)
    3.  [Mobile Device Repair](#org9a69cd9)



<a id="org63edb25"></a>

# The Modern Computer


<a id="org8a8a4f3"></a>

## Introduction to Computer Hardware


### Desktops Computers

They are just computers that can fit on or under our desks.

Following are components of a desktop:

1.  Monitor

2.  Keyboard

3.  Mouse

4.  Desktop


### Laptops

They have all the components baked-in inside a single chassis.


### Ports

To extend the functionality of a computer, we can plug devices into connection points on it.


### CPU (Central Processing Unit)

The brain of our computer, it does all the calculations and data processing.


### RAM (Random Access Memory)

Our computer's short-term memory.


### Hard Drive

Holds all of our data, which includes all of our music, pictures, applications.


### Motherboard

The body or circulatory system of the computer that connects all the pieces together.

1.  It holds everything in place, and lets our components communicate with each other. It's the foundation of our computer.


### Power Supply

It converts the wall power supply to the format which our computer can use.


<a id="orgcab7fb9"></a>

## Programs and Hardware


### Programs

Instructions that tell the computer what to do.


### Hardware

1.  External Data Bus (EDB)/Address Bus

    The instruction travel between CPU and RAM through EDB.

2.  Registers

    They let us store the data that our CPU works with.

3.  Memory Controller Chip

    The MCC is a bridge between the CPU and the RAM.
    
    1.  The MCC grabs the Data from the RAM and sends it through the EDB

4.  Cache

    CPU also uses cache. Cache is smaller than RAM, but it let&rsquo;s us store data that we use often.
    
    1.  Cache levels
    
        There are three different level of cache in a CPU
        
        -   L1
        -   L2
        -   L3
            
            L1 is the smallest and the fastest cache.

5.  Wire Clock

    How does our CPU know when the set of instruction ends, and a new one begins. Here comes the Wire Clock in play.
    
    &rsquo;When you send or receive data, it sends a voltage to that clock wire to let the CPU know it can start doing calculations.&rsquo;

6.  Clock Cycle

    When you send a voltage to the clock wire it&rsquo;s referred to as a clock cycle.

7.  Clock Speed

    The maximum number of clock cycles that it can handle in a certain time period.

8.  Over-clocking

    There&rsquo;re ways to increase the clock speed of the CPU, called over-clocking. It increases the rate of your CPU clock cycles in order to perform more tasks.
    
    -   Overclocking can increase the performance of low end CPUs, but it has certain cons attached to it, like overheating, more power usage etc
    
    -   It can lower CPU lifespan as you're pushing it limits
    
    -   Increased power and heat will degrade most PC components faster


<a id="org39f1e58"></a>

# Components


<a id="orgf521a88"></a>

## CPU


### Instruction Set

Literally a list of instructions that our CPU is able to run.

-   adding
-   subtracting
-   copying data
    -   When you select your CPU, you'll need to make sure it's compatible with your motherboard &#x2013; the circuit board that connects all your components together.


### CPU Socket Types

1.  Land grid array (LGA)

    -   pins stick out of the motherboard

2.  pin grid array (PGA)

    -   pins are located on the processor itself


### Heat Sink

To cool down CPU, attached with a cooler fan.


<a id="org15fe6ee"></a>

## RAM

-   There are lost of types of RAM, and the one that's commonly found in computers is DRAM, or dynamic random-access memory.
-   There are also different types of memory sticks that DRAM chips can be put on. The more modern DIMM stick, which usually stand for Dual Inline Memory Module, have different sizes of pins on them.

1.  SDRAM

    Stands for synchronous DRAM. This type of RAM is synchronized o our systems&rsquo; clock speed allowing quicker processing of data.

2.  DDR SDRAM

    -   In today's system, we use another type of RAM, called the double data rate SDRAM or DDR SDRAM for short.
        1.  DDR1
        2.  DDR2
        3.  DDR3
        4.  DDR4
    
    -   Just like CPU, make sure your RAM module is compatible with your motherboard.


<a id="orgd6e5274"></a>

## Motherboards

Every motherboard has few characteristics:


### Chipset

A chipset is a key component of our motherboard that allows us to manage data between our CPU, RAM and peripherals.

It decides how components talk to each other on our machine:

1.  Northbridge

    It interconnects stuff like RAM and video cars. In some CPUs northbridge directly baked into the CPU itself.

2.  Southbridge

    It maintains our IO or input/output controllers, like hard drives and USB devices that input and output data.


### Peripherals

External devices we connect to our computer, like a mouse, keyboard, and monitor.


### Expansion Slots

Give us the ability to increase the functionality of our computer.

-   The standard for peripheral slot today is PCI Express or Peripheral Component Interconnect Express.


### Form Factor

There're different sizes of motherboards available in market toady.

-   Form factor plays an important role in the choice of PCIes
-   You don't want to respond to a ticked without knowing that a customer bought a GPU which doesn't fit in the PCIe slot.

1.  ATX (Advanced Technology eXtended)

    -   In desktops you'll commonly see full sized ATX's

2.  ITX (Information Technology eXtended)

    -   These much smaller than ATX board, for example Intel NUC uses a variation of ITX, which comes in three form factors:
        1.  mini-ITX
        2.  nano-ITX
        3.  pico-ITX


<a id="org4f8e445"></a>

## Storage

-   HDD (Hard disk drive)
-   SDD (solid state drive)

There are few interfaces that hard drive use to connect our system:

-   ATA &#x2013; the most common ATA is serial ATA or SATA
    -   SATA drive are hot swappable, meaning you don't need turn off your computer to swap them
    -   The interface couldn't keep with speeds of newer SSDs
-   NVM express or NVMe are used for more modern SSDs and reduces the pitfalls of SATA


### kilobyte

The kilobyte is a multiple of the unit byte for digital information.

-   In base 10, one kilobyte is 1000 bytes
-   In base 2, one kilobyte is 1024 bytes


<a id="orgc161a71"></a>

## Power Supplies

It converts the AC we get from the wall into low voltage DC that we can use and transmit throughout our computer.

Power supplies have following components:

-   chassis
-   fan
-   I/O cables
-   power cable


### Voltage

-   Be sure to use proper voltage for your electronics


### Ampere


### Wattage

The amount of volts and amps that a device needs.

-   All kinds of issues are caused by bad power supply, sometimes computer doesn't even turn on.
-   Power supplies can fail for lots of reasons like burnouts, power surge, or even lightning strikes.


<a id="orgd4957d3"></a>

## Mobile Devices

Mobile devices are computer too. They have:

-   CPUs
-   RAM
-   Storage
-   Power systems
-   Peripherals
    -   Mobiles devices can use peripherals too, like headset, micro USB, USB c, and lightening USB etc.
    -   Mobiles devices can themselves be the peripherals, like Smart-watch, fitness band etc

Very small mobile devices uses system-on-chip or SoC


### System on a Chip (SoC)

Packs the CPU, RAM, and sometimes even the storage onto a single chip


<a id="orgcd6b949"></a>

## Batteries and Charging Systems

-   Battery can be charged via wireless pads or cradle
-   Rechargeable batteries have limited life span measured in charge cycle

Components require to charge batteries:

-   Charger
-   PSU or power supply unit to control power flow
-   Wall outlet
-   or Solar panel etc


### Charge Cycle

One full charge and discharge of a battery


<a id="org699270d"></a>

## Peripherals

Anything that you connect to your computer externally that add functionality

Examples:

-   Universal serial bus USB
    -   USB 2.0 - transfer speeds of 480 Mb/s
    -   USB 3.0 - transfer speeds of 5 Gb/s
    -   USB 3.1 - transfer speeds of 10 Gb/s
    -   USB 4 - transfer speed of 40 Gb/s

1.  Difference of MB and Mb/s

    MB is megabyte or unit of data storage, while Mb/s is a megabit per second, which is a unit of data transfer rate.

2.  DVI

    It is generally used for video output, like slide presentation, but for audio you're out of luck

3.  HDMI

    Have audio and video output

4.  Display Port

    Also outputs audio and video

5.  Type C connector

    It can do power and data transfer


<a id="org04fe501"></a>

## Projector

Projectors are display devices for when you need to share information with people in the same location! Most projectors can be used just like any other display on a computer, and with a few differences, can be troubleshot just like any other display device. For example, projectors can have dead or stuck pixels, and can acquire image burn-in, just like other types of displays.


<a id="org6b57928"></a>

# Starting it Up


<a id="orgfe49be7"></a>

## Bios

Our CPU doesn't know that there is a device that it can talk to, so it has to connect to something called the BIOS

The BIOS is software that helps initialize the hardware in our computer and gets our operating system up and running.

It performs following functions:

-   Initialize hardware
-   POST or power on self test
-   Checks what devices are connected to the computer

The BIOS can be stored on motherboard in following components:

-   ROM or read only memory
-   More modern systems use UEFI stands for Unified Extensible Firmware Interface
-   Eventually, UEFI will become the predominant BIOS


### Drivers

They contain the instructions our CPU needs to understand external devices like keyboards ,webcams, printers.


### Power ON Self Test or POST

When computer starts it runs systems checks from time to time refer to as POST.


### CMOS Battery

It stores basic data about booting your computer like the date, time and how you wanted to start up.


### Reimaging

A frequently performed IT task is the reimaging of a computer.

It refers to a disk image which a copy of an operating system, the process involves wiping and reinstalling an operating system.

Following devices can be used for reimaging:

-   USB stick
-   CD/DVD
-   Server accessible through the network


<a id="org3d5210e"></a>

## Putting all together

To build a PC, we need to take care of certain things:

-   prevent static charge
-   To avoid, static discharge, you can touch two devices you plugged in but not powered on from time to time
-   or wear a anti-static wristband


### Building Steps

-   Motherboard: match up holes on motherboard with holes on the desktop
-   CPU: match CPU pointers alignment on the motherboard, don't forget to buy compatible motherboard and CPU
-   Heat-sink: Before attaching on, we need to put even amount of thermal paste on your CPU
-   Plug molex (on Heat sink) to the motherboard to control fan speed
-   Install RAM sticks on motherboard, line up the pins correctly
-   Hard Drive: One SATA cable to connect SSD to mother board
-   Make sure you connect the SATA power to the SSD
-   Case Fans: Check for label on motherboard which says rear fans
-   Power Supply: secure it in the case, big pin power the mother board, other for SATA I/O, 8 pin will power the CPU
-   Plug the cable lying in the case to the mother board, used for buttons, lights etc
-   Fastens the cables
-   GPU: plug in PCIe slot
-   Closed the case
-   Turn it on plugging it to the monitor, keyboard, mouse and power outlet.


<a id="org9a69cd9"></a>

## Mobile Device Repair

-   Know and understand RMA or return merchandise authorization
-   Do a factory reset before sending it off-site repair
-   Before the doing reset inform the end user for possible outcomes of losing all the data


### Factory Reset

Removes all data, apps, and customization from the device

