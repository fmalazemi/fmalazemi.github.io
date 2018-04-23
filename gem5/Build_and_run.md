# Part 2: Build and Run
## Scons
Scons is a software construction tool similar to [Make](https://en.wikipedia.org/wiki/Make_(software)) utility. Scons configuration files are Python scripts. 

## Compile & Build
To compile and build Gem5 issue the scons command with the following parameter <build_dir>/<Configuration>/<target>. For example, 
```
scons build/ARM/gem5.debug
```
* `build` is the
* `ARM` ISA and CPU model. 
* `gem5.debug` output type. It can be with any extensions `debug`, `op`, `fast`, `prof`, or `perf.` For our puspose, we will use only `debug`.

