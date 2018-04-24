# Garnet2.0
Gem5 uses Garnet for on-chip interconnects. The details are published in ISPASS 2009.
In Gem5, you can run Garnet as a stand alone to test you Network-on-chip design using synthatic traffic patterns and this will be our focus here.

## Build Garnet as a stand alone
```
scons build/NULL/gem5.debug PROTOCOL=Garnet_standalone
```
## Run 
```
./build/NULL/gem5.debug configs/example/garnet_synth_traffic.py  \
--num-cpus=16 \
--num-dirs=16 \
--network=garnet2.0 \
--topology=Mesh_XY \
--mesh-rows=4  \
--sim-cycles=1000 \
--synthetic=uniform_random \
--injectionrate=0.01
```
