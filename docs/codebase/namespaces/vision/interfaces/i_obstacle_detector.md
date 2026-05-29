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
#### Get Floor Detector Pointer

```cpp
[[nodiscard]] virtual std::shared_ptr<i_floor_detector> get_floor_detector_ptr() = 0;
```
Returns the floor-detector dependency used by the obstacle pipeline.

!!! note
    Pure virtual method, must be implemented by derived classes.
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
#### Get Contours

```cpp
[[nodiscard]] virtual std::vector<std::vector<cv::Point>> get_contours() = 0;
```
Returns the latest detected obstacle contours in image space.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Union Box

```cpp
[[nodiscard]] virtual cv::Rect get_union_box() = 0;
```
Returns the bounding box that encloses all currently detected obstacle regions.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Union Crop

```cpp
[[nodiscard]] virtual cv::Mat get_union_crop() = 0;
```
Returns the cropped image region corresponding to the current union obstacle bounding box.

!!! note
    Pure virtual method, must be implemented by derived classes.
