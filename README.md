DynPick ROS driver
==================================

ROS driver for [Wacoh-tech force sensor](http://www.wacoh-tech.com/en/products/dynpick/).

Usage
==============

Prerequisite
----------------

 * (only tested on) Ubuntu 12.04 64bit.
 * ROS Hydro or Indigo needs to be installed.

Install
--------

 1. Create `/etc/udev/rules.d/80-wakoh.rules` with the following line:

 ```
## see https://github.com/tork-a/dynpick_driver
ATTRS{idVendor}=="10c4", ATTRS{idProduct}=="ea60", MODE="0666"
 ```

 2. Run `$ sudo service udev restart`

 3. Plug the sensor USB to the Ubuntu computer. Also make sure that the following device was detected.

 ```
$ lsusb 
:
Bus 003 Device 004: ID 10c4:ea60 Cygnal Integrated Products, Inc. CP210x Composite Device
 ```

 4. Obtain `dynpick_driver` package.
 4-a. Via DEB (RECOMMENDED). Run `sudo apt-get install ros-hydro-dynpick-driver`.
 4-b. (Source build. Not recommended) clone this repository and build.

   ```
$ cd %YOUR_CATKING_WORKSPACE%/src
$ git clone https://github.com/tork-a/dynpick_driver.git
$ cd %YOUR_CATKING_WORKSPACE%
$ catkin_make
   ```

Run ROS node
------------

```
 $ roslaunch dynpick_driver sample.launch
```

Video is posted on ROS wiki (http://wiki.ros.org/action/subscribe/dynpick_driver)

[![Build Status](https://travis-ci.org/tork-a/dynpick_driver.png)](https://travis-ci.org/tork-a/dynpick_driver)
--------------------------------------------------------------------------------------------------------------------------------------------

Document
========

See [ROS wiki](http://wiki.ros.org/dynpick_driver) for the document, tutorials.

[API doc is available](http://docs.ros.org/hydro/api/dynpick_driver/html/annotated.html) also on ROS domain.

DEB build status
================

| ROS Distro   | Source deb | Development Branch (travis)  | Development branch (ros.org) | Release Branch | binarydeb Precise AMD64 | Documentation (ros.org) |
| ------------- | ------------- | ---------------------------- | ---------------------------- | -------------- | ----------------------- | ----------------------- |
| Indigo  | N/A | N/A | N/A | N/A | N/A | N/A |
| Hydro | [![Build Status](http://jenkins.ros.org/buildStatus/icon?job=ros-hydro-dynpick_driver_sourcedeb)](http://jenkins.ros.org/job/ros-hydro-dynpick_driver_sourcedeb/) | [![Build Status](https://travis-ci.org/tork-a/dynpick_driver.png?branch=hydro-devel)](https://travis-ci.org/tork-a/dynpick_driver) | [![Build Status](http://jenkins.ros.org/buildStatus/icon?job=devel-hydro-dynpick_driver)](http://jenkins.ros.org/job/devel-hydro-dynpick_driver/) | [![Build Status](https://travis-ci.org/lagadic/dynpick_driver.png?branch=hydro)](https://travis-ci.org/lagadic/dynpick_driver) | [![Build Status](http://jenkins.ros.org/buildStatus/icon?job=ros-hydro-dynpick_driver_binarydeb_precise_amd64)](http://jenkins.ros.org/job/ros-hydro-dynpick_driver_binarydeb_precise_amd64/) | [![Build Status](http://jenkins.ros.org/buildStatus/icon?job=doc-hydro-dynpick_driver)](http://jenkins.ros.org/job/doc-hydro-dynpick_driver/) |

[Devel Test Status](http://wiki.ros.org/regression_tests#Development_Tests)
-------------------------------------------------------------------------------------

[![Hydro Test Satus](http://jenkins.ros.org/job/devel-hydro-dynpick_driver/test/trend?job)](http://jenkins.ros.org/job/devel-hydro-dynpick_driver/)
