# About Widget

- **Class**: `about_widget`
- **Namespace**: `acs::gui`
- **Include**: `#include "gui/implementations/widgets/about_widget.h"`

## Overview

Concrete `widget_host` implementation that renders project/about metadata and runtime informational content in the GUI.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    about_widget["about_widget"]
    about_widget["about_widget"] --> widget_host["widget_host"]
    i_widget["i_widget"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    widget_host["widget_host"] --> i_widget["i_widget"]
    widget_host["widget_host"] --> object["object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`about_widget`](about_widget.md)
  - [`widget_host`](../widget_host.md)
    - [`i_widget`](../../interfaces/i_widget.md)
      - [`i_object`](../../../core/interfaces/i_object.md)
    - [`object`](../../../core/implementations/object.md)
      - [`i_object`](../../../core/interfaces/i_object.md)

## API

### Constructors
#### Default Constructor

```cpp
about_widget();
```
Creates an about widget with default title and initial visibility state.

### Protected Methods
#### On Render

```cpp
void on_render() override;
```
Renders the about panel content for the current frame.
