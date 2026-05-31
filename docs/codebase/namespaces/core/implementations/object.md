# Object

- **Class**: `object`
- **Namespace**: `acs::core`
- **Include**: `#include "core/implementations/object.h"`

## Overview

Concrete `i_object` base implementation that provides stable component identity via a tag and serves as the root for non-threaded ACS components.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    object["object"]
    object["object"] --> i_object["i_object"]
```

### Derived Diagram

```mermaid
graph LR
    object["object"]
    object["object"] --> glfw_window["glfw_window"]
    object["object"] --> threaded_object["threaded_object"]
    object["object"] --> toml_reader["toml_reader"]
    object["object"] --> widget_controller["widget_controller"]
    object["object"] --> widget_host["widget_host"]
    object["object"] --> zenoh_client["zenoh_client"]
    threaded_object["threaded_object"] --> camera["camera"]
    threaded_object["threaded_object"] --> floor_detector["floor_detector"]
    threaded_object["threaded_object"] --> obstacle_detector["obstacle_detector"]
    threaded_object["threaded_object"] --> threaded_widget_host["threaded_widget_host"]
    threaded_widget_host["threaded_widget_host"] --> camera_widget["camera_widget"]
    widget_host["widget_host"] --> about_widget["about_widget"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`object`](object.md)
  - [`i_object`](../interfaces/i_object.md)

### Derived Hierarchy

- [`object`](object.md)
  - [`glfw_window`](../../gui/implementations/glfw_window.md)
  - [`threaded_object`](threaded_object.md)
    - [`camera`](../../vision/implementations/camera.md)
    - [`floor_detector`](../../vision/implementations/floor_detector.md)
    - [`obstacle_detector`](../../vision/implementations/obstacle_detector.md)
    - [`threaded_widget_host`](../../gui/implementations/threaded_widget_host.md)
      - [`camera_widget`](../../gui/implementations/widgets/camera_widget.md)
  - [`toml_reader`](../../utility/implementations/toml_reader.md)
  - [`widget_controller`](../../gui/implementations/widget_controller.md)
  - [`widget_host`](../../gui/implementations/widget_host.md)
    - [`about_widget`](../../gui/implementations/widgets/about_widget.md)
  - [`zenoh_client`](../../utility/implementations/zenoh_client.md)

## API

### Constructors
#### Constructor

```cpp
explicit object(std::string_view tag);
```
Creates a base object with a unique component tag.

##### Parameters
- `tag` (`std::string_view`): Unique component tag used for logging, diagnostics, and lifecycle identification.

### Public Methods

#### Implementations
- [`i_object`](../interfaces/i_object.md)
    - [`get_tag`](../interfaces/i_object.md#get-tag)
