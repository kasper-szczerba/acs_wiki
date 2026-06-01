# Glfw Window

- **Class**: `glfw_window`
- **Namespace**: `acs::gui`
- **Include**: `#include "gui/implementations/glfw_window.h"`

## Overview

Concrete `i_glfw_window` implementation that owns the native GLFW window and applies window/runtime options from project configuration.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    glfw_window["glfw_window"]
    glfw_window["glfw_window"] --> i_glfw_window["i_glfw_window"]
    glfw_window["glfw_window"] --> object["object"]
    i_glfw_window["i_glfw_window"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`glfw_window`](glfw_window.md)
  - [`i_glfw_window`](../interfaces/i_glfw_window.md)
    - [`i_object`](../../core/interfaces/i_object.md)
  - [`object`](../../core/implementations/object.md)
    - [`i_object`](../../core/interfaces/i_object.md)

## API

### Constructors
#### Constructor

```cpp
glfw_window(std::string_view tag, const parameters& parameters);
```
Creates a GLFW window wrapper with the provided identity and window parameters.

##### Parameters
- `tag` (`std::string_view`): Unique component tag used for logging and lifecycle identification.
- `parameters` (`const parameters&`): Window configuration bundle (size, title behavior, context options, and related GLFW settings).

### Nested Types

#### Structs
##### Parameters

```cpp
struct parameters {
  std::string_view title;
  int width;
  int height;
  bool start_maximized;
  bool enable_vsync;
};
```

- `title` (`std::string_view`): The title.
- `width` (`int`): The width.
- `height` (`int`): The height.
- `start_maximized` (`bool`): The start maximized.
- `enable_vsync` (`bool`): The enable vsync.

### Public Methods

#### Implementations
- [`i_glfw_window`](../interfaces/i_glfw_window.md)
    - [`get_window_ptr`](../interfaces/i_glfw_window.md#get-window-pointer)
