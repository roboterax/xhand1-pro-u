<!--
SPDX-FileCopyrightText: Copyright 2026 Beijing Xingdongjiyuan Co. Ltd.
SPDX-License-Identifier: MIT
-->

# URDF V1.2 compatibility update

A trailing ASCII space was removed from the `mass` value of the `left_hand_mid_pip_link` and `right_hand_mid_pip_link` inertial elements:

- Before: `value="0.01706371 "`
- After: `value="0.01706371"`

The numeric mass remains **0.01706371 kg** in both files. No other URDF bytes, joint definitions, numeric parameters or STL mesh data were changed. Other files from the original model package are retained; this compatibility note is added to identify the update.

NVIDIA's public [GEAR DexUMI NOTICE](https://github.com/NVlabs/GR00T-DataHardwarePrototypes/blob/main/NOTICE) records the same whitespace correction for Pinocchio parsing. This update addresses that specific formatting issue; it is not a full simulator or hardware runtime validation.

The original V1.2 MIT package is retained separately by the publisher. Its SHA-256 was `10c6a6d3cf4e2c84ece1b4d185d2d20714232518f7a523e1e398163f7f606d0f`.
