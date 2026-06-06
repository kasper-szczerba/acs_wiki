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
#### Get Obstacle Min Range

```cpp
[[nodiscard]] virtual float get_obstacle_min_range() const = 0;
```
Returns the minimum obstacle range threshold used for filtering detections.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Obstacle Max Range

```cpp
[[nodiscard]] virtual float get_obstacle_max_range() const = 0;
```
Returns the maximum obstacle range threshold used for filtering detections.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Obstacle Height Threshold

```cpp
[[nodiscard]] virtual float get_obstacle_height_threshold() const = 0;
```
Returns the height threshold used to classify points as obstacle candidates above the floor plane.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Road Width

```cpp
[[nodiscard]] virtual float get_road_width() const = 0;
```
Returns the configured road-width estimate used by zone-based obstacle interpretation.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Union Box

```cpp
[[nodiscard]] virtual cv::Rect get_union_box() = 0;
```
Returns the bounding box that encloses all currently detected obstacle regions.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Union Crop Buffer

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_union_crop_buffer() = 0;
```
Returns the GPU-backed crop buffer corresponding to the current union obstacle region.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Left Crop Buffer

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_left_crop_buffer() = 0;
```
Returns the GPU-backed crop buffer for the left obstacle-analysis region.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Center Crop Buffer

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_center_crop_buffer() = 0;
```
Returns the GPU-backed crop buffer for the center obstacle-analysis region.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Right Crop Buffer

```cpp
[[nodiscard]] virtual cv::cuda::GpuMat get_right_crop_buffer() = 0;
```
Returns the GPU-backed crop buffer for the right obstacle-analysis region.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Zone Results

```cpp
[[nodiscard]] virtual std::map<road_zone, zone_result> get_zone_results() = 0;
```
Returns the latest per-zone obstacle-analysis results keyed by road zone.

!!! note
    Pure virtual method, must be implemented by derived classes.
