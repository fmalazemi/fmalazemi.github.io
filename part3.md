# Part 3: Debugging Gem5
###### [Main](index) | [build and run](part2) | Debugging | [Garnet](part4) | [Resources](part5)
Gem5 includes debugging support to print messages according to a specific flag (for all debugging options click [here](http://learning.gem5.org/book/part2/debugging.html#debug-output). You can define as many flags as you want. 

## Add a new debugging flag "newFlag"
Let use say, you want to use "newFlag" in src/temp/temp.cc, 2 steps are required:  
1. Add the following include statement to temp.cc
```
#include "debug/newFlag.hh"
```
2. Register the new flag "newFlag" in src/temp/sconscript by adding the following:
```
DebugFlag('Hello')
```
Now you can use Gem5 debugging prints in temp.cc by adding the following any where in the code
```
DPRINTF(newFlag, "print Message\n");
```

## Run Gem5 with debugging flag "newFlag"
```
build/X86/gem5.opt --debug-flags=newFlag configs/configration.py 
```
## DPRINTF output
 The output for each, say DPRINTF(NewFlag, "Message") is as follows:
 ```
  [current clock cycle: Object_id: Message]
 ```

# Other General debugging techiques
## assert and printf
Assert is a great statement for debugging. You can add it any where to validate the state of your variables or some conndition to be hold. It takes as an input an expression and will do nothing if the expression evalutes to true, otherwise, the program will then terminate abnormally, with no clean-up. Most importantly, it will output the exact location (filename and line number) of the assert statement that took false expression. This is a great why to assure correctness of your code. 
# gdp
[gdb](https://www.gnu.org/software/gdb/) or GNU Project Debugger is also very usefull. Especailly for segmantation faults. 
To use gdb 
```
gdb ./build/NULL/gem5.debug
run configs/configuration.py
```
