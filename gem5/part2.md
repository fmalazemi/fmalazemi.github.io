# Part 2: Build and Run
###### [Part 1](index) | [part 3](debuggin)
## Compile & Build
To compile and build Gem5 issue the scons command with the following parameter `<build_dir>/<Configuration>/<target>`. For example, 
```
scons build/ARM/gem5.debug
```
* `build` = destination folder.
* `ARM` ISA and CPU model.  
* `gem5.debug` output name and type. The name of binary is `gem5`, it can be with any extensions `debug`, `op`, `fast`, `prof`, or `perf.` For our puspose, we will use only `debug`.

## Scons
[Scons](http://www.scons.org) is a software construction tool similar to [Make](https://en.wikipedia.org/wiki/Make_(software)) utility. Scons configuration files are Python scripts. 

## Sconscript
In each folder, `sconscript` file includes information about source files to be included in when building Gem5. The main Scons script file is located at 
```
src/SConscript
```
I advise you to play with it. 
## Adding Source Files
Adding source files and SimObjects are easy in Gem5. All what you need to do is to add a single line for every file. 
```
SimObject('s.py') # add s.py simObject.
Source('x.cc')    # add x.cc source code. 
```

 









