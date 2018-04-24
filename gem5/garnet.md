# Garnet2.0
Gem5 uses Garnet for on-chip interconnects. The details are published in ISPASS 2009.
In Gem5, you can run Garnet as a stand alone to test you Network-on-chip design using synthatic traffic patterns and this will be our focus here.

### Build Garnet as a stand alone
```
scons build/NULL/gem5.debug PROTOCOL=Garnet_standalone
```
### Run 
Gem5 comes with a ready configuration file "configs/example/garnet_synth_traffic.py" to run Garnet as a stand alone. 
```
./build/NULL/gem5.debug configs/example/garnet_synth_traffic.py  --network=garnet2.0 [--option=value]
```
### Options and parameters
We will briefly explain some of the options here, the full list can be found [here](http://www.gem5.org/Garnet_Synthetic_Traffic)
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

### Configuration file 

