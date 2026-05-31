# Camera Widget

- **Class**: `camera_widget`
- **Namespace**: `acs::gui`
- **Include**: `#include "gui/implementations/widgets/camera_widget.h"`

## Overview

Camera Widget.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    camera_widget["camera_widget"]
    camera_widget["camera_widget"] --> threaded_widget_host["threaded_widget_host"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
    i_threaded_widget["i_threaded_widget"] --> i_threaded_object["i_threaded_object"]
    object["object"] --> i_object["i_object"]
    threaded_object["threaded_object"] --> i_threaded_object["i_threaded_object"]
    threaded_object["threaded_object"] --> object["object"]
    threaded_widget_host["threaded_widget_host"] --> i_threaded_widget["i_threaded_widget"]
    threaded_widget_host["threaded_widget_host"] --> threaded_object["threaded_object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`camera_widget`](camera_widget.md)
  - [`threaded_widget_host`](../threaded_widget_host.md)
    - [`i_threaded_widget`](../../interfaces/i_threaded_widget.md)
      - [`i_threaded_object`](../../../core/interfaces/i_threaded_object.md)
        - [`i_object`](../../../core/interfaces/i_object.md)
    - [`threaded_object`](../../../core/implementations/threaded_object.md)
      - [`i_threaded_object`](../../../core/interfaces/i_threaded_object.md)
        - [`i_object`](../../../core/interfaces/i_object.md)
      - [`object`](../../../core/implementations/object.md)
        - [`i_object`](../../../core/interfaces/i_object.md)

## API

### Constructors
#### Constructor

```cpp
camera_widget(std::string_view tag, float update_rate, std::string_view title, std::shared_ptr<vision::i_camera> camera);
```
Creates a camera widget with the specified name.

##### Parameters
- `tag` (`std::string_view`): The tag.
- `update_rate` (`float`): The update rate.
- `title` (`std::string_view`): The title.
- `camera` (`std::shared_ptr<vision::i_camera>`): Shared pointer to the camera.

### Protected Methods
#### Update

```cpp
void update() override;
```
Performs one update cycle.
#### On Render

```cpp
void on_render() override;
```
