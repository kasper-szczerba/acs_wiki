# Floor Plane Math

- **Class**: `floor_plane_math`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/utility/floor_plane_math.h"`

## Overview

Floor Plane Math.

## API

### Public Methods
#### Orient Plane Up

```cpp
[[nodiscard]] static sl::float4 orient_plane_up(const sl::float4& equation);
```

##### Parameters
- `equation`: The equation.
#### Normal Length

```cpp
[[nodiscard]] static float normal_length(const sl::float4& plane);
```

##### Parameters
- `plane`: The plane.
#### Reproject Depth Pixel

```cpp
[[nodiscard]] static sl::float3 reproject_depth_pixel(int x, int y, float z, float fx, float fy, float cx, float cy);
```

##### Parameters
- `x`: The x.
- `y`: The y.
- `z`: The z.
- `fx`: The fx.
- `fy`: The fy.
- `cx`: The cx.
- `cy`: The cy.
#### Absolute Distance To Plane

```cpp
[[nodiscard]] static float absolute_distance_to_plane(const sl::float3& point, const sl::float4& plane, float plane_normal_length);
```

##### Parameters
- `point`: The point.
- `plane`: The plane.
- `plane_normal_length`: The plane normal length.
