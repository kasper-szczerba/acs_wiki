# Obstacle Detector Interface

- **Interface**: `i_obstacle_detector`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/interfaces/i_obstacle_detector.h"`

## Overview

Interface that defines obstacle-detection outputs derived from camera and scene analysis pipelines.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    i_obstacle_detector["i_obstacle_detector"]
    i_obstacle_detector["i_obstacle_detector"] --> i_threaded_object["i_threaded_object"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
```

### Derived Diagram

```mermaid
graph LR
    i_obstacle_detector["i_obstacle_detector"]
    i_obstacle_detector["i_obstacle_detector"] --> obstacle_detector["obstacle_detector"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`i_obstacle_detector`](i_obstacle_detector.md)
  - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
    - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`i_obstacle_detector`](i_obstacle_detector.md)
  - [`obstacle_detector`](../implementations/obstacle_detector.md)

## API

### Public Methods
#### Get Color Frame

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_color_frame() = 0;
```
Returns the latest color frame used by the obstacle detector.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Depth Frame

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_depth_frame() = 0;
```
Returns the latest depth frame used by the obstacle detector.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Model

```cpp
[[nodiscard]] virtual std::string_view get_model() = 0;
```
Returns the camera/model identifier associated with the current detector stream.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get FPS

```cpp
[[nodiscard]] virtual float get_fps() = 0;
```
Returns the current effective processing or capture frame rate.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Dropped Frames Count

```cpp
[[nodiscard]] virtual uint32_t get_dropped_frames_count() = 0;
```
Returns the number of frames dropped during detector input acquisition.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Is Opened

```cpp
[[nodiscard]] virtual bool get_is_opened() = 0;
```
Returns whether the detector input stream is currently open and usable.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Native Camera Reference

```cpp
[[nodiscard]] virtual sl::Camera &get_native_camera_ref() = 0;
```
Returns a reference to the underlying native camera object used by the detector.

!!! note
    Pure virtual method, must be implemented by derived classes.
