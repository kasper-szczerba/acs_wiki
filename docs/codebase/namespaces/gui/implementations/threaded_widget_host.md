# Threaded Widget Host

- **Class**: `threaded_widget_host`
- **Namespace**: `acs::gui`
- **Include**: `#include "gui/implementations/threaded_widget_host.h"`

## Overview

Concrete implementation of `i_threaded_widget`.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    threaded_widget_host["threaded_widget_host"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
    i_threaded_widget["i_threaded_widget"] --> i_threaded_object["i_threaded_object"]
    object["object"] --> i_object["i_object"]
    threaded_object["threaded_object"] --> i_threaded_object["i_threaded_object"]
    threaded_object["threaded_object"] --> object["object"]
    threaded_widget_host["threaded_widget_host"] --> i_threaded_widget["i_threaded_widget"]
    threaded_widget_host["threaded_widget_host"] --> threaded_object["threaded_object"]
```

### Derived Diagram

```mermaid
graph LR
    threaded_widget_host["threaded_widget_host"]
    threaded_widget_host["threaded_widget_host"] --> camera_widget["camera_widget"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`threaded_widget_host`](threaded_widget_host.md)
  - [`i_threaded_widget`](../interfaces/i_threaded_widget.md)
    - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
      - [`i_object`](../../core/interfaces/i_object.md)
  - [`threaded_object`](../../core/implementations/threaded_object.md)
    - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
      - [`i_object`](../../core/interfaces/i_object.md)
    - [`object`](../../core/implementations/object.md)
      - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`threaded_widget_host`](threaded_widget_host.md)
  - [`camera_widget`](widgets/camera_widget.md)

## API

### Constructors
#### Constructor

```cpp
threaded_widget_host(std::string_view tag, float update_rate, std::string_view title);
```
Creates a threaded widget host with the specified name.

##### Parameters
- `tag`: The tag.
- `update_rate`: The update rate.
- `title`: The title.

### Public Methods

#### Implementations
- [`i_threaded_widget`](../interfaces/i_threaded_widget.md)
    - [`render`](../interfaces/i_threaded_widget.md#render)
    - [`get_title`](../interfaces/i_threaded_widget.md#get-title)
    - [`get_is_open_ref`](../interfaces/i_threaded_widget.md#get-is-open-reference)

### Protected Methods
#### On Render

```cpp
virtual void on_render() = 0;
```

!!! note
    Pure virtual method, must be implemented by derived classes.
