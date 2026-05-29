# TOML Reader Interface

- **Interface**: `i_toml_reader`
- **Namespace**: `acs::utility`
- **Include**: `#include "utility/interfaces/i_toml_reader.h"`

## Overview

Interface for loading, owning, and exposing parsed TOML configuration tables.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    i_toml_reader["i_toml_reader"]
    i_toml_reader["i_toml_reader"] --> i_object["i_object"]
```

### Derived Diagram

```mermaid
graph LR
    i_toml_reader["i_toml_reader"]
    i_toml_reader["i_toml_reader"] --> toml_reader["toml_reader"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`i_toml_reader`](i_toml_reader.md)
  - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`i_toml_reader`](i_toml_reader.md)
  - [`toml_reader`](../implementations/toml_reader.md)

## API

### Public Methods
#### Parse

```cpp
virtual void parse() = 0;
```
Parses the configuration file.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Free

```cpp
virtual void free() = 0;
```
Releases the parsed configuration data.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get File Path

```cpp
[[nodiscard]] virtual std::string_view get_file_path() const noexcept = 0;
```
Returns the currently configured TOML file path used by the reader.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Set File Path

```cpp
virtual void set_file_path(std::string_view file_path) = 0;
```
Updates the TOML file path to be used on the next parse operation.

##### Parameters
- `file_path`: New TOML file path to load when parsing is triggered.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Table Reference

```cpp
[[nodiscard]] virtual toml::table &get_table_ref() = 0;
```
Returns mutable access to the parsed TOML root table.

!!! note
    Pure virtual method, must be implemented by derived classes.
