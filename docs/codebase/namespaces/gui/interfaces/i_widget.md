# Widget Interface

- **Interface**: `i_widget`
- **Namespace**: `acs::gui`
- **Include**: `#include "gui/interfaces/i_widget.h"`

## Overview

Interface for widget.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    i_widget["i_widget"]
    i_widget["i_widget"] --> i_object["i_object"]
```

### Derived Diagram

```mermaid
graph LR
    i_widget["i_widget"]
    i_widget["i_widget"] --> widget_host["widget_host"]
    widget_host["widget_host"] --> about_widget["about_widget"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`i_widget`](i_widget.md)
  - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`i_widget`](i_widget.md)
  - [`widget_host`](../implementations/widget_host.md)
    - [`about_widget`](../implementations/widgets/about_widget.md)

## API

### Public Methods
#### Render

```cpp
virtual void render() = 0;
```

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Title

```cpp
[[nodiscard]] virtual std::string_view get_title() const noexcept = 0;
```
Returns the title.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Is Open Reference

```cpp
[[nodiscard]] virtual bool& get_is_open_ref() noexcept = 0;
```
Returns the is open reference.

!!! note
    Pure virtual method, must be implemented by derived classes.
