# Intel® Movidius™ Neural Compute SDK
This Intel® Movidius™ Neural Compute software developer kit (NCSDK) is provided for users of the [Intel® Movidius™ Neural Compute Stick](https://developer.movidius.com/) (Intel® Movidius™ NCS). It includes software tools, an API, and examples, so developers can create software that takes advantage of the accelerated neural network capability provided by the Intel Movidius NCS hardware.

# How to install C/C++ API library bindings ON macOS

The below guide describes how to intall C/C++ NCSDK API library bindindgs on macOS

## Prerequisities

Make sure you have the following packages installed:

`opencv` version should be 3.4.2

```shell
$ brew install coreutils opencv libusb pkg-config wget
```

## Install

Run the following command to build and install NCSDK C/C++ API library bindings:

```shell
$ cd api/src && sudo make basicinstall
```

## Test

Plug your Intel® Movidius™ Neural Compute Stick into your laptop and run the following command:

```
$ cd examples/apps/hello_ncs_cpp/ && make run

making hello_ncs_cpp
g++ cpp/hello_ncs.cpp -o cpp/hello_ncs_cpp -lmvnc
Created cpp/hello_ncs_cpp executable

making run
cd cpp; ./hello_ncs_cpp; cd ..
ncsdk/examples/apps/hello_ncs_cpp/cpp
Hello NCS! Device opened normally.
Goodbye NCS!  Device Closed normally.
NCS device working.
```

## Uninstall

To uninstall the C++ API library bindings run the command below:

```shell
$ cd api/src && sudo make uninstall
```
