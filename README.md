# FreeRTOSV202112

Free RTOS in Linux

https://freertos.org/FreeRTOS-simulator-for-Linux.html

+-FreeRTOS-Plus    Contains FreeRTOS+ components and demo projects.
|
+-FreeRTOS         Contains the FreeRTOS real time kernel source
                   files and demo projects


Object: Only use a port Posix_GCC to test in Linux
        The other ports were delete

The libraries required for test in linux 
$ gcc --version
gcc (GCC) 9.2.0
    • make

$ make --version
GNU Make 3.81
Copyright (C) 2006  Free Software Foundation, Inc.
    • libpcap (for networking support)

$ version: libpcap-devel-1.5.3-11.x86_64
To install on ubuntu run
$ sudo apt-get install libpcap-dev

-------------------------
Building the source code: 
    1. Navigate to the Demo Directories at: Kernel Demo source 
       $ cd FreeRTOS/Demo/Posix_GCC/
    2. To build run:
       $ make
    3. To clean run: 
       $ make clean

------------------------
Running the Demo :
    1. Navigate to the newly created "build" directory 
       $ cd build 
    2. Run the Kernel demo (Blinky or Full)
       $ ./posix_demo
    3. By default runs the Blinky, here is the log 

    Trace started.
The trace will be dumped to disk if a call to configASSERT() fails.
Starting echo blinky demo
Message received from task
Message received from task
Message received from task
Message received from task
Message received from task
Message received from task
Message received from task
Message received from task
Message received from task
Message received from software timer
Message received from task
Message received from task

There are a task and a timer


