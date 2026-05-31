# Camera

- **Class**: `camera`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/implementations/camera.h"`

## Overview

Concrete `i_camera` implementation backed by ZED SDK capture. It acquires RGB and depth frames, tracks stream health metrics, and exposes the native camera handle for lower-level integrations.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    camera["camera"]
    camera["camera"] --> i_camera["i_camera"]
    camera["camera"] --> threaded_object["threaded_object"]
    i_camera["i_camera"] --> i_threaded_object["i_threaded_object"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    threaded_object["threaded_object"] --> i_threaded_object["i_threaded_object"]
    threaded_object["threaded_object"] --> object["object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`camera`](camera.md)
  - [`i_camera`](../interfaces/i_camera.md)
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
camera(std::string_view tag, float update_rate, const parameters_t& parameters);
```
Creates a camera component that initializes and manages the ZED capture pipeline.

##### Parameters
- `tag` (`std::string_view`): Unique component tag used for logging and lifecycle identification.
- `update_rate` (`float`): Requested update frequency in Hz for frame acquisition and status refresh.
- `parameters` (`const parameters_t&`): Camera configuration bundle (resolution, depth mode, runtime options, and related capture settings).

### Nested Types

#### Enums
##### Resolution E

```cpp
enum class resolution_e : uint8_t {
  vga,
  hd720,
  hd1080
};
```

###### Values
- `vga`: The vga.
- `hd720`: The hd720.
- `hd1080`: The hd1080.
##### Depth Mode E

```cpp
enum class depth_mode_e : uint8_t {
  none,
  neural_light,
  neural,
  neural_plus,
};
```

###### Values
- `none`: The none.
- `neural_light`: The neural light.
- `neural`: The neural.
- `neural_plus`: The neural plus.

#### Structs
##### Parameters T

```cpp
struct parameters_t {
  resolution_e resolution;
  depth_mode_e depth_mode;
  int device_fps;
  bool enable_verbose_sdk_logging;
  float depth_minimum_distance;
  float depth_maximum_distance;
  int confidence_threshold;
  int texture_confidence_threshold;
};
```

- `resolution` (`resolution_e`): The resolution.
- `depth_mode` (`depth_mode_e`): The depth mode.
- `device_fps` (`int`): The device FPS.
- `enable_verbose_sdk_logging` (`bool`): The enable verbose sdk logging.
- `depth_minimum_distance` (`float`): The depth minimum distance.
- `depth_maximum_distance` (`float`): The depth maximum distance.
- `confidence_threshold` (`int`): The confidence threshold.
- `texture_confidence_threshold` (`int`): The texture confidence threshold.

### Public Methods

#### Implementations
- [`i_camera`](../interfaces/i_camera.md)
    - [`get_color_frame`](../interfaces/i_camera.md#get-color-frame)
    - [`get_depth_frame`](../interfaces/i_camera.md#get-depth-frame)
    - [`get_model`](../interfaces/i_camera.md#get-model)
    - [`get_fps`](../interfaces/i_camera.md#get-fps)
    - [`get_dropped_frames_count`](../interfaces/i_camera.md#get-dropped-frames-count)
    - [`get_is_opened`](../interfaces/i_camera.md#get-is-opened)
    - [`get_zed_camera_ref`](../interfaces/i_camera.md#get-zed-camera-reference)

### Protected Methods
#### Update

```cpp
void update() override;
```
Polls the camera, updates color and depth frame buffers, and refreshes stream status metrics for downstream consumers.
