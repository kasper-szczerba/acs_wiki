# Obstacle Detector

- **Class**: `obstacle_detector`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/implementations/obstacle_detector.h"`

## Overview

Concrete implementation of `i_obstacle_detector`.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    obstacle_detector["obstacle_detector"]
    i_obstacle_detector["i_obstacle_detector"] --> i_threaded_object["i_threaded_object"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    obstacle_detector["obstacle_detector"] --> i_obstacle_detector["i_obstacle_detector"]
    obstacle_detector["obstacle_detector"] --> threaded_object["threaded_object"]
    threaded_object["threaded_object"] --> i_threaded_object["i_threaded_object"]
    threaded_object["threaded_object"] --> object["object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`obstacle_detector`](obstacle_detector.md)
  - [`i_obstacle_detector`](../interfaces/i_obstacle_detector.md)
    - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
      - [`i_object`](../../core/interfaces/i_object.md)
  - [`threaded_object`](../../core/implementations/threaded_object.md)
    - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
      - [`i_object`](../../core/interfaces/i_object.md)
    - [`object`](../../core/implementations/object.md)
      - [`i_object`](../../core/interfaces/i_object.md)

## API

### Constructors
#### Constructor

```cpp
obstacle_detector(std::string_view tag,
                  float update_rate,
                  const parameters_t& parameters,
                  std::shared_ptr<i_camera> camera_ptr,
                  std::shared_ptr<i_floor_detector> floor_detector_ptr);
```
Creates an obstacle detector with the specified name.

##### Parameters
- `tag`: The tag.
- `update_rate`: The update rate.
- `parameters`: The parameters.
- `camera_ptr`: Shared pointer to the camera.
- `floor_detector_ptr`: Shared pointer to the floor detector.

### Public Methods

#### Implementations
- [`i_obstacle_detector`](../interfaces/i_obstacle_detector.md)
    - [`get_color_frame`](../interfaces/i_obstacle_detector.md#get-color-frame)
    - [`get_depth_frame`](../interfaces/i_obstacle_detector.md#get-depth-frame)
    - [`get_model`](../interfaces/i_obstacle_detector.md#get-model)
    - [`get_fps`](../interfaces/i_obstacle_detector.md#get-fps)
    - [`get_dropped_frames_count`](../interfaces/i_obstacle_detector.md#get-dropped-frames-count)
    - [`get_is_opened`](../interfaces/i_obstacle_detector.md#get-is-opened)
    - [`get_native_camera_ref`](../interfaces/i_obstacle_detector.md#get-native-camera-reference)

### Protected Methods
#### Update

```cpp
void update() override;
```
Performs one update cycle.
