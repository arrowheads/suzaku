#Suzaku

A clean init system using s6 as the process supervisor.

### Why?
I wasn't happy with other init systems, So I decided to write my own.

### Features:

* Clean, readable scripts.
  * You can very easily learn from reading the code.
* Fast.
  * If you have dash installed, the boot times are very small.

### Structure:
At boot, sinit calls `fly`, which mounts the pseudo-filesystems, checks the filesystems,
mounts those, starts eudev and syncs the system clock.

When taking off is done, The system enters the `flight` stage. The script mounts swap, does some configuration,
and starts s6, which starts the services you configured.

When you want to shutdown, the system must `land`. This script kills the processes, 
unmounts the partitions, and then shuts down the system or reboots based on what was requested to sinit.

##### Why this naming?
Because it's fun!

### Installation:
For now, Suzaku is still undergoing bug testing, but you can 
install it and use it!

Dependencies: toybox, s6, eudev, util-linux (for now, I'm looking to replace this with toybox)

The default setup is this:

1. Copy `fly`, `flight`, `land` and `services` to `/etc/suzaku`.
2. Install pavo as `/sbin/pavo`
3. Compile sinit with the provided header. (`sinit.config.h`)
4. Edit the config to your desire.

### Things to do
1. It needs to be made more generic! For now, I pushed a configuration that
matches what I use on my computer.
2. Add more services.
3. Extend pavo so it's able to enable services.
4. Make a makefile.
