This layer is for testing any  linux-stable version on qemuarm (MACHINE NAME will show as livearm ) 


This is tested on poky master branch

Add this layer to your bblayers.conf

Change machine name to "livearm" in conf/local.conf of your  build


If you are using appends for any variable Follow the below standard.

IMAGE_INSTALL:append , rather than IMAGE_INSTALL_append
In master branch of poky,  *_append  is replaced with *:append (Underscores have replace with COLON) 


Mask the linux-stable.bbappend file .. There might be patches , which you might not need 

To run the qemu 
$ runqemu livearm nographic

//In case your image doesnot boots, with some tempdevs/udevtemps  errors , use the below command to run the image 

$ runqemu livearm nographic slirp


