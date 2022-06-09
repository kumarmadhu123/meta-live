This layer is for testing any  linux-stable version on qemuarm (MACHINE NAME will show as livearm ) 


This is tested on poky master branch

Add this layer to your bblayers.conf

Change machine name to "livearm" in conf/local.conf of your  build

To set your kernel version of your choice 
-------------------------------
1. Go to recipes-kernel/linux/linux-stable.bb
2. Change the below variables
LINUX_VERSION ?= "4.14.277"
SRCREV_machine="e3a56aaade89bc89f33baec11b12538fc22536e2"
SRCREV should be the Topmost commit of the released kernel .
e.g e3a56aaade89bc89f33baec11b12538fc22536e2 is the SRCREV of topmost commit of v4.14.277  https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git/commit/?h=linux-4.14.y&id=e3a56aaade89bc89f33baec11b12538fc22536e2
3. Give correct branch name at  branch=linux-4.14.y




If you are using appends for any variable Follow the below standard.

IMAGE_INSTALL:append , rather than IMAGE_INSTALL_append
In master branch of poky,  *_append  is replaced with *:append (Underscores have replace with COLON) 


Mask the linux-stable.bbappend file .. There might be patches , which you might not need 

To run the qemu 
$ runqemu livearm nographic

//In case your image doesnot boots, with some tempdevs/udevtemps  errors , use the below command to run the image 

$ runqemu livearm nographic slirp


