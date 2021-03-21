There are a few distributions of Plan 9, I need some for home use which will satisfy my requirements.

# Requirements

My hardware consists of predominantly second-hand machines, some new Raspberry PIs. 
The goal is to hook them all together in a Plan 9 network!

* Cloud (Linode, Azure) 
* Raspberry PIs 3 & 4
* One or two i386 Wintel
* Various AMD64 Wintel
* an iMac
* SGI 02
* microcontrollers
  * arduino
  * maximite
  * wib
  * gigatron
* Retro
  * Apple 2
  * BBC-B
  
# Getting started in a RaspBerry Pi 3



# Getting Started in an Intel VM

To get started I'm using a virtual machine on my Debian AMD64 Laptop. Debian 9 (stretch). 
This means I should not need to contend with hardware driver issues. With luck it will just 
work in a VM, becuase the Plan 9 should support the defacto virtual hardware.

I tried using Oracle VirtualBox 5.2.44 but there is an issue preventing networking. Following this tip 
(https://unix.stackexchange.com/questions/122259/how-do-i-install-plan-9-on-oracle-vm-virtualbox). I 
have switched to QEMU (I use the AQemu GUI) and KVM.  Just the version that comes with Stretch.


# The candidate distros:

* Plan 9 from Bell Labs - https://9p.io/plan9/
* 9legacy - http://9legacy.org/index.html
* 9front - http://9front.org/

I chose to install 9front and 9legacy in VMs downloaded from the above sites:

* 9front-8013.d9e940a768d1.amd64.iso.gz
* 9legacy.iso.bz2

## 9legacy

9legacy seems to be kept up-to-date. Last update was 2021-02-21. 
see http://www.9legacy.org/patch.html So that looks good! 

## 9front

9front was updated 2021-10-18, (http://9front.org/iso/) so not bad either.

I just followed their install instructions. No dramas there.

The 9front distro seems to have a lot of applications including `mothra` the web browser. 

However the 9front web site is a bit weird - not easy to follow what's what and who's who. Also the
distro has some very-offensive text in the /lib/terry file. (Probably illegal hate-speech 
in some jurisdictions!) You can see it's even in the source tree https://code.9front.org/hg/plan9front/rev/7d4e834a0222. 

There are instructions in a video which shows how to change the screen resolution and 
fonts amongst other things: 


## Next

I'm going to focus on the 9legacy distro, not least because Francisco J Ballesteros has published a beginners 
book (https://lsub.org/) which uses the original Plan 9 distribution. (Introduction to Operating Systems Abstractions
Using Plan 9 from Bell Labs). 

# TODO

* TODO - How to get operating system version information like Linux /etc/os-release ? I don't know exactly which versions I am running!  




