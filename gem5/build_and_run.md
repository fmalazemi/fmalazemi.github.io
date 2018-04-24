# Part 2: Build and Run
###### [Part 3](debugging) | [part 5](part5)
## Compile & Build
To compile and build Gem5 issue the scons command with the following parameter `<build_dir>/<Configuration>/<target>`. For example, 
```
scons build/ARM/gem5.debug
```
* `build` = destination folder.
* `ARM` ISA and CPU model.  
* `gem5.debug` output type. It can be with any extensions `debug`, `op`, `fast`, `prof`, or `perf.` For our puspose, we will use only `debug`.

## Scons
Scons is a software construction tool similar to [Make](https://en.wikipedia.org/wiki/Make_(software)) utility. Scons configuration files are Python scripts. 

## Sconscript
In each folder, `sconscript` file includes information about source files to be included in when building Gem5. The main Scons script file is located at 
```
src/SConscript
```
I advise you to play with it. 
## Adding Source Files
The following is an example file 
```
Import('*')
if env['PROTOCOL'] == 'None':
    Return()
SimObject('s.py')
Source('x.cc')
```

To add C++ file, append with file with `Source('file.cc')`. Similarly, for SimObject add `SimObject('file.py')`.
 









