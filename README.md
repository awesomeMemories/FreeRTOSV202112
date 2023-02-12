# FreeRTOSV202112

## Table of Contents

- [Introduction](#Introduction)
- [Methodology](#Methodology)
- [Results](#Results)
- [Conclusion](#Conclusion)

## Introduction
This is an incomplete copy of FreeRTOS. It only has Linux port(the port is also referred to as the POSIX port). See about [Linux port](https://freertos.org/FreeRTOS-simulator-for-Linux.html).

If you need the complete documentation, please visit [Official website](https://www.freertos.org/).

If you need complete FreeRTOS: Go to the website https://www.freertos.org, then click on the "Download FreeRTOS" button on the top menu bar.

### Scope
This software aims to learn about the FreeRTOS using Linux to create task, queues between task, etc.


## Methodology
* Prerequisites:
   1. gcc
      $ gcc --version  
      gcc (GCC) 9.2.0

   2. make
      $ make --version  
      GNU Make 3.81

   3. libpcap
      $ version: libpcap-devel-1.5.3-11.x86_64

      To install on Ubuntu run  
      $ sudo apt-get install libpcap-dev

* Building the source code: 
   1. Navigate to the Demo Directories at: Kernel Demo source   
      $ cd FreeRTOS/Demo/Posix_GCC/
   2. To build run:  
      $ make
   3. To clean run:  
      $ make clean
      
* Running the Demo :
   1. Navigate to the newly created "build" directory  
      $ cd build 
   2. Run the Kernel demo (Blinky or Full)  
      $ ./posix_demo  
      NOTE: By default runs the Blinky 

   3. If you need to change to FULL_DEMO behavior: Go to FreeRTOS/Demo/Posix_GCC/main.c file, then uncomment de FULL_DEMO define and comment de BLINKY_DEMO define, make clean and make run again.

      //#define    mainSELECTED_APPLICATION     BLINKY_DEMO  
      #define    mainSELECTED_APPLICATION     FULL_DEMO


## Results
Below is the normal behavior for BLINKY_DEMO example.

Trace started.  
The trace will be dumped to disk if a call to configASSERT() fails.  
Starting echo blinky demo  
RX:1 Message received from task  
RX:2 Message received from task  
RX:3 Message received from task  
RX:4 Message received from task  
RX:Message received from software timer  
RX:1 Message received from task  
RX:2 Message received from task  
RX:3 Message received from task  
RX:4 Message received from task  
RX:5 Message received from task  
RX:Message received from software timer  
RX:1 Message received from task  
RX:2 Message received from task  


### There are two task and a timer:

- Task called prvQueueSendTask: This task is in the blocked state until it is time to run again, then send a message to the queue.

- Timer called prvQueueSendTimerCallback: When the timer expires the message is sent 

- Task called prvQueueReceiveTask: Wait until something arrives in the queue, then print if it is from SendTask or Timer
