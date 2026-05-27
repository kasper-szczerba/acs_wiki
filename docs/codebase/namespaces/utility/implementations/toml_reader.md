# TOML Reader

- **Class**: `toml_reader`
- **Namespace**: `acs::utility`
- **Include**: `#include "utility/implementations/toml_reader.h"`

## Overview

Concrete implementation of `i_toml_reader`.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    toml_reader["toml_reader"]
    i_toml_reader["i_toml_reader"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    toml_reader["toml_reader"] --> i_toml_reader["i_toml_reader"]
    toml_reader["toml_reader"] --> object["object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`toml_reader`](toml_reader.md)
  - [`i_toml_reader`](../interfaces/i_toml_reader.md)
    - [`i_object`](../../core/interfaces/i_object.md)
  - [`object`](../../core/implementations/object.md)
    - [`i_object`](../../core/interfaces/i_object.md)

## API

### Constructors
#### Constructor

```cpp
toml_reader(std::string_view name, std::string_view file_path);
```
Creates a toml reader with the specified name.

##### Parameters
- `name`: The name of the component.
- `file_path`: The file path.

### Public Methods

#### Implementations
- [`i_toml_reader`](../interfaces/i_toml_reader.md)
    - [`parse`](../interfaces/i_toml_reader.md#parse)
    - [`free`](../interfaces/i_toml_reader.md#free)
    - [`get_file_path`](../interfaces/i_toml_reader.md#get-file-path)
    - [`set_file_path`](../interfaces/i_toml_reader.md#set-file-path)
    - [`get_table_ref`](../interfaces/i_toml_reader.md#get-table-reference)
