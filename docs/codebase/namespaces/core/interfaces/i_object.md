# Object Interface

- **Interface**: `i_object`
- **Namespace**: `acs::core`
- **Include**: `#include "core/interfaces/i_object.h"`

## Overview

Base interface for all ACS components, providing shared identity and lifecycle integration points.

## Inheritance Diagram

### Derived Diagram

```mermaid
graph LR
    i_object["i_object"]
    i_camera["i_camera"] --> camera["camera"]
    i_floor_detector["i_floor_detector"] --> floor_detector["floor_detector"]
    i_glfw_window["i_glfw_window"] --> glfw_window["glfw_window"]
    i_gps["i_gps"] --> gps["gps"]
    i_object["i_object"] --> i_glfw_window["i_glfw_window"]
    i_object["i_object"] --> i_gps["i_gps"]
    i_object["i_object"] --> i_threaded_object["i_threaded_object"]
    i_object["i_object"] --> i_toml_reader["i_toml_reader"]
    i_object["i_object"] --> i_widget["i_widget"]
    i_object["i_object"] --> i_widget_controller["i_widget_controller"]
    i_object["i_object"] --> i_zenoh_client["i_zenoh_client"]
    i_object["i_object"] --> object["object"]
    i_obstacle_detector["i_obstacle_detector"] --> obstacle_detector["obstacle_detector"]
    i_threaded_object["i_threaded_object"] --> i_camera["i_camera"]
    i_threaded_object["i_threaded_object"] --> i_floor_detector["i_floor_detector"]
    i_threaded_object["i_threaded_object"] --> i_obstacle_detector["i_obstacle_detector"]
    i_threaded_object["i_threaded_object"] --> i_threaded_widget["i_threaded_widget"]
    i_threaded_object["i_threaded_object"] --> i_traffic_light_detector["i_traffic_light_detector"]
    i_threaded_object["i_threaded_object"] --> threaded_object["threaded_object"]
    i_threaded_widget["i_threaded_widget"] --> threaded_widget_host["threaded_widget_host"]
    i_toml_reader["i_toml_reader"] --> toml_reader["toml_reader"]
    i_traffic_light_detector["i_traffic_light_detector"] --> traffic_light_detector["traffic_light_detector"]
    i_widget["i_widget"] --> widget_host["widget_host"]
    i_widget_controller["i_widget_controller"] --> widget_controller["widget_controller"]
    i_zenoh_client["i_zenoh_client"] --> zenoh_client["zenoh_client"]
    object["object"] --> glfw_window["glfw_window"]
    object["object"] --> threaded_object["threaded_object"]
    object["object"] --> toml_reader["toml_reader"]
    object["object"] --> widget_controller["widget_controller"]
    object["object"] --> widget_host["widget_host"]
    object["object"] --> zenoh_client["zenoh_client"]
    threaded_object["threaded_object"] --> camera["camera"]
    threaded_object["threaded_object"] --> floor_detector["floor_detector"]
    threaded_object["threaded_object"] --> gps["gps"]
    threaded_object["threaded_object"] --> obstacle_detector["obstacle_detector"]
    threaded_object["threaded_object"] --> threaded_widget_host["threaded_widget_host"]
    threaded_object["threaded_object"] --> traffic_light_detector["traffic_light_detector"]
    threaded_widget_host["threaded_widget_host"] --> camera_widget["camera_widget"]
    threaded_widget_host["threaded_widget_host"] --> obstacle_diagnostic_widget["obstacle_diagnostic_widget"]
    widget_host["widget_host"] --> about_widget["about_widget"]
```

## Inheritance Hierarchy

### Derived Hierarchy

- [`i_object`](i_object.md)
  - [`i_glfw_window`](../../gui/interfaces/i_glfw_window.md)
    - [`glfw_window`](../../gui/implementations/glfw_window.md)
  - [`i_gps`](../../utility/interfaces/i_gps.md)
    - [`gps`](../../utility/implementations/gps.md)
  - [`i_threaded_object`](i_threaded_object.md)
    - [`i_camera`](../../vision/interfaces/i_camera.md)
      - [`camera`](../../vision/implementations/camera.md)
    - [`i_floor_detector`](../../vision/interfaces/i_floor_detector.md)
      - [`floor_detector`](../../vision/implementations/floor_detector.md)
    - [`i_obstacle_detector`](../../vision/interfaces/i_obstacle_detector.md)
      - [`obstacle_detector`](../../vision/implementations/obstacle_detector.md)
    - [`i_threaded_widget`](../../gui/interfaces/i_threaded_widget.md)
      - [`threaded_widget_host`](../../gui/implementations/threaded_widget_host.md)
        - [`camera_widget`](../../gui/implementations/widgets/camera_widget.md)
        - [`obstacle_diagnostic_widget`](../../gui/implementations/widgets/obstacle_diagnostic_widget.md)
    - [`i_traffic_light_detector`](../../vision/interfaces/i_traffic_light_detector.md)
      - [`traffic_light_detector`](../../vision/implementations/traffic_light_detector.md)
    - [`threaded_object`](../implementations/threaded_object.md)
      - [`camera`](../../vision/implementations/camera.md)
      - [`floor_detector`](../../vision/implementations/floor_detector.md)
      - [`gps`](../../utility/implementations/gps.md)
      - [`obstacle_detector`](../../vision/implementations/obstacle_detector.md)
      - [`threaded_widget_host`](../../gui/implementations/threaded_widget_host.md)
        - [`camera_widget`](../../gui/implementations/widgets/camera_widget.md)
        - [`obstacle_diagnostic_widget`](../../gui/implementations/widgets/obstacle_diagnostic_widget.md)
      - [`traffic_light_detector`](../../vision/implementations/traffic_light_detector.md)
  - [`i_toml_reader`](../../utility/interfaces/i_toml_reader.md)
    - [`toml_reader`](../../utility/implementations/toml_reader.md)
  - [`i_widget`](../../gui/interfaces/i_widget.md)
    - [`widget_host`](../../gui/implementations/widget_host.md)
      - [`about_widget`](../../gui/implementations/widgets/about_widget.md)
  - [`i_widget_controller`](../../gui/interfaces/i_widget_controller.md)
    - [`widget_controller`](../../gui/implementations/widget_controller.md)
  - [`i_zenoh_client`](../../utility/interfaces/i_zenoh_client.md)
    - [`zenoh_client`](../../utility/implementations/zenoh_client.md)
  - [`object`](../implementations/object.md)
    - [`glfw_window`](../../gui/implementations/glfw_window.md)
    - [`threaded_object`](../implementations/threaded_object.md)
      - [`camera`](../../vision/implementations/camera.md)
      - [`floor_detector`](../../vision/implementations/floor_detector.md)
      - [`gps`](../../utility/implementations/gps.md)
      - [`obstacle_detector`](../../vision/implementations/obstacle_detector.md)
      - [`threaded_widget_host`](../../gui/implementations/threaded_widget_host.md)
        - [`camera_widget`](../../gui/implementations/widgets/camera_widget.md)
        - [`obstacle_diagnostic_widget`](../../gui/implementations/widgets/obstacle_diagnostic_widget.md)
      - [`traffic_light_detector`](../../vision/implementations/traffic_light_detector.md)
    - [`toml_reader`](../../utility/implementations/toml_reader.md)
    - [`widget_controller`](../../gui/implementations/widget_controller.md)
    - [`widget_host`](../../gui/implementations/widget_host.md)
      - [`about_widget`](../../gui/implementations/widgets/about_widget.md)
    - [`zenoh_client`](../../utility/implementations/zenoh_client.md)

## API

### Public Methods
#### Get Tag

```cpp
[[nodiscard]] virtual std::string_view get_tag() const noexcept = 0;
```
Returns the component tag used for identification in logs, diagnostics, and component wiring.

!!! note
    Pure virtual method, must be implemented by derived classes.
