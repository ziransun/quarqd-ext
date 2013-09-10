## Quarqd-ext

An extension on [quarqd](http://opensource.quarq.us/quarqd/) to support weight scale, blood pressure, blood glucose and pedometer health devices. 

Webinos [healthhub](https://github.com/webinos/hub-webinosHealth) is an example of using this extended damon with ant+ sensor drivers. Webinos provides [ant+ sensor drivers](https://github.com/ziransun/webinos-driver-ant) in associate with this extension work.



### Build:

please check README.build for building instructure. 

### Run:

Once build is successful, executable will be created at quarqd_ext/quarqd_dist/quarqd/src/

run

sudo ./quarqd

By default, it is assumed the your ANT+ USB is mounted at /dev/ttyANT. If it's not, it will throw an error. To work around this, 
First check where your ANT+ USB is mounted to. For example, if it's mounted as /dev/ttyUSB0, do a symbolic link to ttyANT. In /dev

sudo ln -s ttyUSB0 ttyANT






