# Part 3: Debugging Gem5
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
## Gem5 debugging output


# `assert` and `printf` 

# `gdp` 
