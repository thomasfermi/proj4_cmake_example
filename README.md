# PROJ CMake example
This repo shows a minimum working example program in C++ using the [PROJ][2] library. The example program is taken from the [documentation's quick start guide][0]. The tiny contribution of this repo is just a suggestion on how to 
* install the [proj][2] library via vcpkg and 
* how to build a minimal example with CMake

## PROJ4 vs PROJ
Be aware: The PROJ4 library changed its name to PROJ.

## 1. Installing PROJ
I recommend using the C++ package manager [vcpkg][1]. Please follow the quick start section on the [vcpkg][1] repo to install it. 

Afterwards execute 
```bash
$ ./vcpkg install proj
```
 

to install the [PROJ][2] library.

[0]:https://proj.org/development/quickstart.html
[1]:https://github.com/microsoft/vcpkg
[2]:https://proj.org/

## 2. Building the example program
Clone this repo, cd into it, create a build directory and call cmake from there:
```sh
$ git clone https://github.com/thomasfermi/proj4_cmake_example.git
$ cd proj4_cmake_example
$ mkdir build
$ cd build
$ cmake .. "-DCMAKE_TOOLCHAIN_FILE=/home/my_user_name/vcpkg/scripts/buildsystems/vcpkg.cmake"
```
In the last command I assumed that you have your vcpkg installation under `/home/my_username/vcpkg`. Change the command according to your actual installation path (the path to where you cloned the vcpkg github repo). If CMake did not finish successfully, please check out the appendix of this README.md. If CMake did finish successfully, you can execute

```sh
$ make
```

Before executing your program, you need to set the `PROJ_LIB` enviroment variable to the folder containing `proj.db` (adjust the path below according to your installation of vcpkg):
```sh
export PROJ_LIB=/home/my_user_name/vcpkg/packages/proj_x64-linux/share/proj/
./example_main
```

