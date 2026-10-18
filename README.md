# Official FreeDV radio integrations

This repository contains the official FreeDV radio integrations (originally included as part of freedv-gui,
but now spun off into a separate repositorhy to make more clear that these are licensed differently from 
freedv-gui). We currently support the following radios:

* [FlexRadio 6000/8000/Aurora series](./src/flex/README.md)
* [KA9Q/Web SDR support](./src/ka9q/README.md)

## Building

You can build the radio integrations for execution on your local machine by running the following:

```
# Clone repo:
$ git clone --recurse-submodules https://github.com/freedv/freedv-integrations

# or:
$ git clone https://github.com/freedv/freedv-integrations
$ git submodule update --init --recursive

# Build:
$ mkdir build
$ cd build
$ cmake ..
$ make
```
