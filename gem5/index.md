# Part 1: What is Gem5
GEM5 is a simulator dedicated for computer architecture research communities. It  encompasses system and process level microarchitecture. 
## Credit 
Gem5 is a merge of the best aspects of M5 and GEM5. The project is a result of joint efforts of many companies and schools (AMD, ARM, HP, MIPS, Princeton, MIT, uTexas, wisc, and umich.)
## Features
Highly configurable and includes multiple CPU and ISA models.
## Languages 
Python for scripts to pass parameters and configuration files and the rest is written in C++.  
## Download
Clone the below
```
git clone https://github.com/gem5/gem5.git
```
## Requirement
For Ubuntu systems, the required packeges are  
```
sudo apt install build-essential git m4 scons zlib1g zlib1g-dev libprotobuf-dev protobuf-compiler libprotoc-dev libgoogle-perftools-dev python-dev python
```
For other OS's or more information, click [here](http://gem5.org/Compiling_M5#Required_Software)
## Event-driven architecture 
Gem5 is event driven. That is, to run an object you must trigger an event to do so. In Gem5, there is a general event queue that includes all events. Remember, only SimObject can be triggered and enqueued in the event queue.  For more info, click [here](here). 


