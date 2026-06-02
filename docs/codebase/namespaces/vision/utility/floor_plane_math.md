# Floor Plane Math

- **Class**: `floor_plane_math`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/utility/floor_plane_math.h"`

## Overview

Utility helpers for floor-plane geometry math used by vision components when normalizing plane orientation and computing camera-space distances.

## API

### Public Methods
#### Ensure Plane Faces Up

```cpp
[[nodiscard]] static sl::float4 ensure_plane_faces_up(const sl::float4& equation);
```
Normalizes a plane equation so its normal points upward in camera/world convention.

##### Parameters
- `equation` (`const sl::float4&`): Input plane equation coefficients `(a, b, c, d)` to normalize.
#### Calculate Normal Magnitude

```cpp
[[nodiscard]] static float calculate_normal_magnitude(const sl::float4& plane);
```
Computes the Euclidean magnitude of the plane normal `(a, b, c)`.

##### Parameters
- `plane` (`const sl::float4&`): Plane equation coefficients `(a, b, c, d)` whose normal magnitude is needed.
#### Back Project Pixel To 3d

```cpp
[[nodiscard]] static sl::float3 back_project_pixel_to_3d(int x, int y, float z, const camera_intrinsics& intrinsics);
```
Back-projects a depth pixel into 3D camera coordinates using camera intrinsics.

##### Parameters
- `x` (`int`): Pixel x-coordinate in image space.
- `y` (`int`): Pixel y-coordinate in image space.
- `z` (`float`): Depth value at the pixel in camera depth units.
- `intrinsics` (`const camera_intrinsics&`): Camera intrinsic parameters (`fx`, `fy`, `cx`, `cy`) used for back-projection.
#### Project 3d To Pixel

```cpp
[[nodiscard]] static cv::Point2f project_3d_to_pixel(const sl::float3& point, const camera_intrinsics& intrinsics);
```
Projects a 3D camera-space point onto image coordinates using camera intrinsics.

##### Parameters
- `point` (`const sl::float3&`): 3D point in camera coordinates to project into image space.
- `intrinsics` (`const camera_intrinsics&`): Camera intrinsic parameters (`fx`, `fy`, `cx`, `cy`) used for projection.
#### Get Distance To Plane

```cpp
[[nodiscard]] static float get_distance_to_plane(const sl::float3& point, const sl::float4& plane, float plane_normal_length);
```
Computes signed point-to-plane distance, normalized by the provided plane normal magnitude.

##### Parameters
- `point` (`const sl::float3&`): 3D point to evaluate against the plane equation.
- `plane` (`const sl::float4&`): Plane equation coefficients `(a, b, c, d)` used for distance evaluation.
- `plane_normal_length` (`float`): Precomputed magnitude of the plane normal used for normalization.
