# Floor Detector Interface

- **Interface**: `i_floor_detector`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/interfaces/i_floor_detector.h"`

## Overview

Interface that defines floor-plane detection outputs derived from live camera input.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    i_floor_detector["i_floor_detector"]
    i_floor_detector["i_floor_detector"] --> i_threaded_object["i_threaded_object"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
```

### Derived Diagram

```mermaid
graph LR
    i_floor_detector["i_floor_detector"]
    i_floor_detector["i_floor_detector"] --> floor_detector["floor_detector"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`i_floor_detector`](i_floor_detector.md)
  - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
    - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`i_floor_detector`](i_floor_detector.md)
  - [`floor_detector`](../implementations/floor_detector.md)

## API

### Public Methods
#### Get Detected Floor Plane

```cpp
[[nodiscard]] virtual sl::Plane get_detected_floor_plane() = 0;
```
Returns the latest detected floor plane object from the backend.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Plane Equation

```cpp
[[nodiscard]] virtual sl::float4 get_plane_equation() = 0;
```
Returns the latest floor plane equation coefficients.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Is Floor Detected

```cpp
[[nodiscard]] virtual bool get_is_floor_detected() = 0;
```
Returns whether a valid floor plane was detected in the latest update cycle.

!!! note
    Pure virtual method, must be implemented by derived classes.
