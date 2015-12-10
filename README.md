# stage_ros
Package which contains ROS specific hooks and tools for the Stage simulator.

This version has two new features, but default settings make it work as in the previous versions, when the new features are not used.

New features:

1) Parametric names for all the frames used in the stage_ros node and for some topics.

<pre>
      Parameter                   Default
      ---------                   -------
      base_frame                  base_link
      base_footprint_frame        base_footprint
      laser_frame                 base_laser_link
      camera_frame                camera_link
      odom_frame                  odom
      laser_topic                 base_scan
</pre>

  Frame and topic names can be set as parameters (for example, in the launch file).

2) Provide additional control of the simulation without using the GUI

stage_ros is listening for the String topic /stageGUIRequest

The content of the string data may be:
<pre>
  screenshot : activate screenshots for 2 seconds
  footprints : activate footprints
  speedup    : set simulation speedup to 2.0
</pre>

For enabling, the new features in 2), a customized version of Stage, which is available in
https://github.com/iocchi/Stage, is required.

To set cmake for using stage, add the path of the stage-config.cmake file
to CMAKE_PREFIX_PATH. This file is in the install directory of Stage 
(make sure you run 'make install' when building Stage).

Example:
  $ export CMAKE_PREFIX_PATH=$CMAKE_PREFIX_PATH:$HOME/lib/stage4/lib64/cmake

