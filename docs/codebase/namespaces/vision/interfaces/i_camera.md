# Camera Interface

- **Interface**: `i_camera`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/interfaces/i_camera.h"`

## Overview

Interface that defines camera stream access for RGB/depth frames, camera metadata, and runtime health metrics.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    i_camera["i_camera"]
    i_camera["i_camera"] --> i_threaded_object["i_threaded_object"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
```

### Derived Diagram

```mermaid
graph LR
    i_camera["i_camera"]
    i_camera["i_camera"] --> camera["camera"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`i_camera`](i_camera.md)
  - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
    - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`i_camera`](i_camera.md)
  - [`camera`](../implementations/camera.md)

## API

### Public Methods
#### Get Color Frame

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_color_frame() = 0;
```
Returns the most recent color frame stored in GPU memory.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Depth Frame

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_depth_frame() = 0;
```
Returns the most recent depth frame stored in GPU memory.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Model

```cpp
[[nodiscard]] virtual std::string_view get_model() = 0;
```
Returns the camera model identifier reported by the backend.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get FPS

```cpp
[[nodiscard]] virtual float get_fps() = 0;
```
Returns the current effective capture frame rate.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Dropped Frames Count

```cpp
[[nodiscard]] virtual unsigned int get_dropped_frames_count() = 0;
```
Returns the number of frames dropped by the capture pipeline.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Is Opened

```cpp
[[nodiscard]] virtual bool get_is_opened() = 0;
```
Returns whether the underlying camera stream is currently open and usable.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get ZED Camera Reference

```cpp
[[nodiscard]] virtual sl::Camera& get_zed_camera_ref() = 0;
```
Returns a reference to the underlying ZED camera object for advanced operations.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Intrinsics

```cpp
[[nodiscard]] virtual camera_intrinsics get_intrinsics() = 0;
```
Returns the active camera intrinsic calibration values used for geometric projection and back-projection.

!!! note
    Pure virtual method, must be implemented by derived classes.
