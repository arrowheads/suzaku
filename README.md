#Suzaku

A clean init system using s6 as the process supervisor.

### Why?
I wasn't happy with other init solutions at the time I wrote this,
So I decided to write my own.

### Features:

* Clean, readable scripts.
  * You can very easily learn from reading the code.
* Fast.
  * If you have dash installed, the boot times are very small.

### Instructions:
For now, Suzaku is still undergoing bug testing, but you can 
install it and use it!

Dependencies: toybox, s6, util-linux (for now, I'm looking to replace this with toybox)

The default setup is this:

1. Install `fly`, `flight`, `land` and `svc.d` to `/etc/suzaku`.

2. Install pavo as `/sbin/pavo`
 
3. Compile sinit with the provided header. (`sinit.config.h`)

4. Edit the config to your desire.

### Things to do
1. It needs to be made more generic! For now, I pushed a configuration that
matches what I use on my computer.
2. Add more services.
3. Extend pavo so it's able to enable services.
4. Make a makefile.
