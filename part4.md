# Part 4: Garnet 
###### [Main](index) | [build and run](part2) | [Debugging](part3) | Garnet | [Resources](part5)
Gem5 uses Garnet for on-chip interconnects. The details are published in [ISPASS 2009](https://ieeexplore.ieee.org/document/4919636/).
In Gem5, you can run Garnet as a stand alone to test you Network-on-chip design using synthatic traffic patterns and this will be our focus here.

### Build Garnet as a stand alone
```
scons build/NULL/gem5.debug PROTOCOL=Garnet_standalone
```
Notice that, the ISA model here is chosen to be NULL. This will run Garnet as a stand alone with no processor model. Traffic are to be generated synthatically. 
### Run 
Gem5 comes with a ready configuration file "configs/example/garnet_synth_traffic.py" to run Garnet as a stand alone. 
```
./build/NULL/gem5.debug configs/example/garnet_synth_traffic.py  --network=garnet2.0 [--option=value]
```
### Options and parameters
We will briefly explain some of the options here, the full list can be found [here](http://www.gem5.org/Garnet_Synthetic_Traffic).
* `--num-cpus`	Number of cpus.
* `--num-dirs`	Number of directories.
* `--network`   choose `garnet2.0` for running synthetic traffic patterns.
* `--topology`	Topology for connecting the cpus and dirs to the network routers/switches. More detail about different topologies can be found here.
* `--router-latency` Latency of the router.
* `--link-latency`	latency of the link.
* `--sim-cycles`  The number of cycles to run the simulator.
* `--synthetic` Traffic pattern type. 
* `--injectionrate` Injection rate for each node per cycle. 


### Source files
Garnet source files are located in 
```
src/mem/ruby/network/garnet2.0
```
Topologies are implemented in 
```
src/mem/ruby/network/topology.cc
```
Configuration File. It also includes some of options related to running garnet as a stand alone (e.g. `--sim-cycles`, `--synthetic`, `--injectionrate`, ... etc.) 
```
configs/example/garnet_synth_traffic.py
```
Option related to Network (e.g. `--topology`, `--network`, `--link-latency`, ... etc.)
```
configs/network/Network.py
```
Common Options (e.g. `--num-cpu`, `--num-dir`, ... etc.)
```
gem5/configs/common/Options.py
```
