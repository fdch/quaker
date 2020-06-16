# quacker

[quaker] allows for multiple simultaneous calls between performers using Miller Puckette's quacktrip~ utility (distributed in this repository, also available here: https://msp.ucsd.edu/tools/quacktrip)

## Usage:

[quacker] is meant for audio communication only between computers behind home routers. Audio is routed in/out from outisde Pure Data using Jack, JackPilot, Blackhole, or similar. Pd takes care of the communication between computers, and your audio can be generated/listened in any other application (Pd, Max, daws, etc). 
First thing to do is edit the `setup.txt` text with the previously agreed upon *call-name* and *server*. Eg: 

```
#;
#;
# ONE CALL (2 users);
#;
#;
make quacker 1;
quacker call-name marcfede;
quacker server foo.ucsd.edu;
quacker block 0;
quacker fifo 20;
quacker insig 1 2;
quacker outsig 1 2;
``` 
Note that the `#` symbol acts as a comment and the semicolons are needed for Pd to load the file correctly.

## GUI

[quacker] can be run with or without gui.

### Without gui: 

on macos: double-click on the `run` (shell script). A terminal window will pop-up and quacktrip will be running. Hit `ctrl+C` to quit. 

on unix systems: 
```
cd quacker
./run 
```
Alternatively, you can run the script with flags to pass to Pd. See `pd -help` for more flags. This one here is particularly useful, since it is easy to route quacktrip with jack:
```
./run -jack
```

### With gui

On any platform, you should be able to double-click on the `quaker.pd` file. You need to have Pd version >= 0.51 for everything to work.

## Acknowledgements

Thanks to 
- Miller Puckette for making quacktrip,
- the Pure Data community,
- Federico Ragessi and Gustavo Alcaráz for very useful testing, and
- Marc Ainger, Ann Stimson and Jacob from the Sonic Arts Lab at Ohio State University for the many performances and rehearsals
