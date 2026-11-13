<!--
SPDX-FileCopyrightText: Copyright 2026 Beijing Xingdongjiyuan Co. Ltd.
SPDX-License-Identifier: MIT
-->
# Known issues — unchanged from the supplied model package

This licensing and packaging update does not fix the existing runtime configuration.
The following applies to both hand packages:

- `launch/display.launch` declares a required `model` argument without a default,
  although its value is not used.
- `launch/display.launch` references `urdf.rviz`, which is not supplied.
- `launch/gazebo.launch` publishes `base_link` to `base_footprint`; neither frame
  is the hand's actual URDF root, so that transform does not connect the hand.
- `config/joint_names_*.yaml` contains an empty string as the first joint name.
- `package.xml` omits runtime dependencies used by the launch files:
  `gazebo_ros`, `tf`, and `rostopic`.
- Package author/maintainer fields still contain exporter placeholders.
- Each historical CAD CSV has 40 link records while the current URDF has 50
  links; do not regenerate the current model from these CSV snapshots.

The detailed collision STL geometry contains approximately 470,000 triangles
per hand and has not been simplified for real-time physics. No self-collision,
joint-coupling, dynamics, control, or continuous-motion acceptance is implied.
