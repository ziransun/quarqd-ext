## Quarqd-ext

An extension on [quarqd](http://opensource.quarq.us/quarqd/) to support weight scale, blood pressure, blood glucose and pedometer health devices. 

Webinos [healthhub](https://github.com/webinos/hub-webinosHealth) is an example of using this extended damon with ant+ sensor drivers. Webinos provides [ant+ sensor drivers](https://github.com/ziransun/webinos-driver-ant) in associate with this extension work.



### Build:

please check README.build for building instructure. 

### Run:

Once build is successful, executable will be created at quarqd_ext/quarqd_dist/quarqd/src/. Run

    sudo ./quarqd

By default, it is assumed the your ANT+ USB is mounted at /dev/ttyANT. If it's not, it will throw an error. To work around this, 
First check where your ANT+ USB is mounted to. For example, if it's mounted as /dev/ttyUSB0, do a symbolic link to ttyANT. In /dev

    sudo ln -s ttyUSB0 ttyANT
  
### Mount Ant USB

If USB is not mounted automatically in your /dev, try the follows
  
    sudo sh -c "echo 'options usbserial vendor=0x0fcf product=0x1008' >> /etc/modprobe.d/test.conf"
    sudo sh -c " echo 'SUBSYSTEMS=="tty", ACTION=="add", ATTRS{idProduct}=="1008", ATTRS{idVendor}=="0fcf",  MODE="0664", SYMLINK+="ttyUSB0"' >> /etc/udev/rules.d/90-ant.rules"
    sudo /sbin/modprobe usbserial vendor=0x0fcf product=0x1008
    
Replace the vendor and product code with those come with your ant usb.

### Add user to dialout group

You may need to add your user account to the dialout group in order to open the serial port from your user accout rather than root. 
for example, in Ubuntu 
    
    z.sun> sudo adduser z.sun dialout
    z.sun> sudo reboot
    
    



    
    
    
    





