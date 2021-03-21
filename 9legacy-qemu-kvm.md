# Running 9legacy in a QEMU KVM Virtual Machine

## Networking

### Is the Network Working?

`ip/ping` does not work in QEMU (Why?), So use `hget` to hit a known working IP server

```
hget http://www.example.com/
```
If that works you also have a working Internet connection. If no Internet pick a local web server on your network:
```
hget http://192.168.0.130/
```

### QEMU Setup

Here are working settings for QEMU

```
Disk
  vmdk 20GByte
Network
  card model = vertio
  connection mode = user mode network stack
```

### What actually got set up? 
Get MAC address 
```
% awk -F: '/addr/' /net/ether0/stats
```

## The Boot Sequence

Plan 9 reads files in a FAT partition as part of the boot sequence. 

After it has booted you don't see the FAT files since they aren't mounted by default.
So mount it with the script `/root/rc/bin/9fat:` (no arguments). 

This mounts the FAT partition as a `dossrv` file system at `/n/9` and `/n/9fat`. 

Now you can see the file `plan9.ini` which can be configured as you wish.

### plan9.ini and the Screen Resolution

Even thouogh plan9.ini has variables for setting the screen (`vgasize` and `monitor`) 
these are not actually used by the kernel. The screen is set up after booting. You can 
use the `aux/vga` program to dynamically change configuration. This is what happens in the 
`/rc/bin/termrc` script - the resolution is actually set in userland.

Anyhow set `vgasize=1280x1024x8` set in `/rc/bin/termrc`. 

### Add Audio device

# Connecting

Try to connect to a server over the Internet http://wiki.9gridchan.org/Connecting/index.html

# TODO

* TODO - How to list the hardware being used by the kernel and what devices are attached. Like Linux `hwinfo` ?
* TODO - Set up Audio for 9legacy in QEMU
