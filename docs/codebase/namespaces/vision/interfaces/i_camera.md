# Camera Interface

- **Interface**: `i_camera`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/interfaces/i_camera.h"`

## Overview

Interface for camera.

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
Returns the color frame.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Depth Frame

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_depth_frame() = 0;
```
Returns the depth frame.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Model

```cpp
[[nodiscard]] virtual std::string_view get_model() = 0;
```
Returns the model.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get FPS

```cpp
[[nodiscard]] virtual float get_fps() = 0;
```
Returns the FPS.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Dropped Frames Count

```cpp
[[nodiscard]] virtual unsigned int get_dropped_frames_count() = 0;
```
Returns the dropped frames count.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Is Opened

```cpp
[[nodiscard]] virtual bool get_is_opened() = 0;
```
Returns whether the camera is opened.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get ZED Camera Reference

```cpp
[[nodiscard]] virtual sl::Camera &get_zed_camera_ref() = 0;
```
Returns the ZED camera reference.

!!! note
    Pure virtual method, must be implemented by derived classes.
