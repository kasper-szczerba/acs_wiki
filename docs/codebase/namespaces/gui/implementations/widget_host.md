# Widget Host

- **Class**: `widget_host`
- **Namespace**: `acs::gui`
- **Include**: `#include "gui/implementations/widget_host.h"`

## Overview

Base host implementation for `i_widget` that provides common widget state (title/open flag) and delegates widget-specific drawing to derived classes.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    widget_host["widget_host"]
    i_widget["i_widget"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    widget_host["widget_host"] --> i_widget["i_widget"]
    widget_host["widget_host"] --> object["object"]
```

### Derived Diagram

```mermaid
graph LR
    widget_host["widget_host"]
    widget_host["widget_host"] --> about_widget["about_widget"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`widget_host`](widget_host.md)
  - [`i_widget`](../interfaces/i_widget.md)
    - [`i_object`](../../core/interfaces/i_object.md)
  - [`object`](../../core/implementations/object.md)
    - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`widget_host`](widget_host.md)
  - [`about_widget`](widgets/about_widget.md)

## API

### Constructors
#### Constructor

```cpp
widget_host(std::string_view tag, std::string_view title);
```
Creates a widget host with a stable identity tag and display title.

##### Parameters
- `tag` (`std::string_view`): Unique component tag used for logging and lifecycle identification.
- `title` (`std::string_view`): Display title shown in the widget header or window chrome.

### Public Methods

#### Implementations
- [`i_widget`](../interfaces/i_widget.md)
    - [`render`](../interfaces/i_widget.md#render)
    - [`get_title`](../interfaces/i_widget.md#get-title)
    - [`get_is_open_ref`](../interfaces/i_widget.md#get-is-open-reference)

### Protected Methods
#### On Render

```cpp
virtual void on_render() = 0;
```
Implements widget-specific rendering logic invoked by the base `render` flow.

!!! note
    Pure virtual method, must be implemented by derived classes.
