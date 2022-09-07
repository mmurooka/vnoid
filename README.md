# vnoid
Humanoid Virtual Athletics Challenge

```bash
$ mkdir build
$ cd build
$ cmake ..
$ make
$ make install
```

If you have ROS and non-ROS openhrp3 installed, specify the prefix path of non-ROS openhrp3 by adding the option `-DOPENHRP3_1_PREFIX=<openhrp3 prefix path>` to cmake.
In the same way, if you have ROS and non-ROS hrpsys-base installed, specify the prefix path of non-ROS hrpsys-base by adding the option `-DHRPSYSBASE_PREFIX=<hrpsys-base prefix path>` to cmake.
