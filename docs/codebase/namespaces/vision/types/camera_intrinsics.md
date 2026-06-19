# Camera Intrinsics

- **Namespace**: `acs::vision`
- **Include**: `#include "vision/types/camera_intrinsics.h"`

## Overview

Camera intrinsic calibration values used by vision utilities for pixel back-projection and geometric measurements.

## API

### Public Structs
#### Camera Intrinsics

```cpp
struct camera_intrinsics {
    float focal_length_x;
    float focal_length_y;
    float center_point_x;
    float center_point_y;
  }
```
Intrinsic camera parameters in pixel units.

- `focal_length_x` (`float`): Horizontal focal length (`fx`) in pixels.
- `focal_length_y` (`float`): Vertical focal length (`fy`) in pixels.
- `center_point_x` (`float`): Principal-point x-coordinate (`cx`) in pixels.
- `center_point_y` (`float`): Principal-point y-coordinate (`cy`) in pixels.
