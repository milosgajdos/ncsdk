# Intel® Movidius™ Neural Compute SDK V2
This Intel® Movidius™ Neural Compute software developer kit (NCSDK) is provided for users of the [Intel® Movidius™ Neural Compute Stick](https://developer.movidius.com/) (Intel® Movidius™ NCS). It includes software tools, an API, and examples, so developers can create software that takes advantage of the accelerated neural network capability provided by the Intel Movidius NCS hardware.

# How to install C/C++ NCSDK API V2 library bindings ON macOS

The below guide describes how to intall C/C++ NCSDK API V2 library bindindgs on macOS

## Prerequisities

Make sure you have the following packages installed:

`opencv` version should be 3.4.2

```shell
$ brew install coreutils opencv libusb pkg-config wget
```

## Install

**Note:** You can install the python bindings in `virtualenv`, but you have to enable it by modifying a configuration file as described [here](https://movidius.github.io/ncsdk/virtualenv.html)

Run the following command to build and install NCSDK C/C++ V2 API library bindings:

```shell
cd api/src && sudo make basicinstall pythoninstall
```

## Test

**API V2 does seem to be broken on macOS, though as you can see below:**

Plug your Intel® Movidius™ Neural Compute Stick into your laptop and run the following command:

```
$ cd ../../examples/apps/hello_ncs_cpp/ && make run

making hello_ncs_cpp
g++ cpp/hello_ncs.cpp -o cpp/hello_ncs_cpp -lmvnc
Created cpp/hello_ncs_cpp executable

making run
cd cpp; ./hello_ncs_cpp; cd ..

Can't create semaphore
Function not implemented
Can't create semaphore
Function not implemented
E: [ 0] dispatcherAddEvent:533 can't wait semaphore
W: [ 0] dispatcherAddEvent:545 No more semaphores. Increase XLink or OS resources
E: [ 0] dispatcherAddEvent:533 can't wait semaphore
W: [ 0] dispatcherAddEvent:545 No more semaphores. Increase XLink or OS resources
E: [ 0] XLinkOpenStream:909 Max streamId reached deaddead!
W: [ 0] ncDeviceOpen:558 can't open stream
Error- ncDeviceOpen failed
ncStatus value: -2_
```

## Uninstall

To uninstall the C++ API library bindings run the command below:

```shell
$ cd api/src && sudo make uninstall
```
