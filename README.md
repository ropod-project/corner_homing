# corner_homing

## Summary

A component for aligning a robot close to a corner. The alignment is performed based on laser scan measurements and is a two-step procedure:
1. the robot is aligned with the wall on its lateral side (by minimising the angle between the robot's local x-axis and the line through the lateral scan points)
2. once the alignment is complete, the robot moves close to the corner so that its distance to both corner sides is reduced within a desired bound

The homing procedure is exposed as an action server.

## Dependencies

* `numpy`
* `rospy`
* `tf`
* `geometry_msgs`
* `sensor_msgs`
* `actionlib`

## Launch file parameters

* `laser_topic`
* `cmd_vel_topic`

* `base_link_frame_name`
* `laser_frame_name`

* `homing_server_name`
* `max_linear_vel_ms`
* `max_angular_vel_rads`

* `x_scan_min`
* `x_scan_max`
* `y_scan_min`
* `y_scan_max`

* `x_desired_dist`
* `y_desired_dist`
* `rotational_alignment_threshold`
