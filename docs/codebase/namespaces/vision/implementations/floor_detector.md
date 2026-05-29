# Floor Detector

- **Class**: `floor_detector`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/implementations/floor_detector.h"`

## Overview

Concrete implementation of `i_floor_detector`.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    floor_detector["floor_detector"]
    floor_detector["floor_detector"] --> i_floor_detector["i_floor_detector"]
    floor_detector["floor_detector"] --> threaded_object["threaded_object"]
    i_floor_detector["i_floor_detector"] --> i_threaded_object["i_threaded_object"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    threaded_object["threaded_object"] --> i_threaded_object["i_threaded_object"]
    threaded_object["threaded_object"] --> object["object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`floor_detector`](floor_detector.md)
  - [`i_floor_detector`](../interfaces/i_floor_detector.md)
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
floor_detector(std::string_view tag, float update_rate, std::shared_ptr<i_camera> camera_ptr);
```
Creates a floor detector with the specified name.

##### Parameters
- `tag`: The tag.
- `update_rate`: The update rate.
- `camera_ptr`: Shared pointer to the camera.

### Public Methods

#### Implementations
- [`i_floor_detector`](../interfaces/i_floor_detector.md)
    - [`get_detected_floor_plane`](../interfaces/i_floor_detector.md#get-detected-floor-plane)
    - [`get_plane_equation`](../interfaces/i_floor_detector.md#get-plane-equation)
    - [`get_is_floor_detected`](../interfaces/i_floor_detector.md#get-is-floor-detected)

### Protected Methods
#### Update

```cpp
void update() override;
```
Performs one update cycle.
