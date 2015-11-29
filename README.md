# stage_ros
Package which contains ROS specific hooks and tools for the Stage simulator.

This version has been modified to provide additional features:
- control of the simulation speedup
- control of GUI options (e.g., footprints)
- activate screenshots

It requires a customized version of Stage available in
https://github.com/iocchi/Stage

To set cmake for using stage, add the path of the stage-config.cmake file
to CMAKE_PREFIX_PATH. This file is in the install directory of Stage 
(make sure you run 'make install' when building Stage).

Example:
  $ export CMAKE_PREFIX_PATH=$CMAKE_PREFIX_PATH:$HOME/lib/stage4/lib64/cmake

