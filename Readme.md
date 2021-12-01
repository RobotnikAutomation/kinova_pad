# kinova_pad

Package containing [robotnik_pad](http://www.github.com/RobotnikAutomation/robotnik_pad) plugins for teleoperating Kinova arms.

## Installation

The package depends on some Robotnik packages:

- robotnik_pad [🔗](https://github.com/RobotnikAutomation/robotnik_pad/)
```bash
git clone https://github.com/RobotnikAutomation/rcomponent
```

This package also depends on kinova msgs:

- kinova_ros [🔗](https://github.com/Kinovarobotics/kinova-ros)
```bash
git clone https://github.com/Kinovarobotics/kinova-ros
```

## Parameters

This an example of a config file loading the kinova plugin:

```yaml
plugins:
  - KinovaArm

KinovaArm:
  type: kinova_pad_plugin/KinovaArm
  arm_control_topic_name: /robot/j2s6s200_controller/in/cartesian_velocity_with_fingers
  set_home_service_name: /robot/j2s6s200_controller/in/home_arm
  max_linear_speed: 2.0
  max_angular_speed: 3.0
  config:
    button_deadman: 4
    button_movement_deadman: 5 # this plugin will not work if movement deadman button is pressed
    button_home_arm: 12

    axis_open_gripper: 4
    axis_close_gripper: 3

    axis_linear_x_ee: 1
    axis_linear_y_ee: 0
    axis_linear_z_ee: 10

    axis_angular_x_ee: 5
    axis_angular_y_ee: 2
    axis_angular_z_ee: 9

    button_speed_up: 3
    button_speed_down: 1
```

