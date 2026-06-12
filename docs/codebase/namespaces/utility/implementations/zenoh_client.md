# Zenoh Client

- **Class**: `zenoh_client`
- **Namespace**: `acs::utility`
- **Include**: `#include "utility/implementations/zenoh_client.h"`

## Overview

Concrete `i_zenoh_client` implementation that manages Zenoh endpoint settings and associated session/config handles.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    zenoh_client["zenoh_client"]
    i_zenoh_client["i_zenoh_client"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    zenoh_client["zenoh_client"] --> i_zenoh_client["i_zenoh_client"]
    zenoh_client["zenoh_client"] --> object["object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`zenoh_client`](zenoh_client.md)
  - [`i_zenoh_client`](../interfaces/i_zenoh_client.md)
    - [`i_object`](../../core/interfaces/i_object.md)
  - [`object`](../../core/implementations/object.md)
    - [`i_object`](../../core/interfaces/i_object.md)

## API

### Constructors
#### Constructor

```cpp
zenoh_client(std::string_view address, unsigned int port);
```
Creates a Zenoh client with the specified remote endpoint address and port.

##### Parameters
- `address` (`std::string_view`): Remote Zenoh endpoint address (hostname or IP).
- `port` (`unsigned int`): Remote Zenoh endpoint port number.

### Public Methods

#### Implementations
- [`i_zenoh_client`](../interfaces/i_zenoh_client.md)
    - [`disconnect`](../interfaces/i_zenoh_client.md#disconnect)
    - [`get_address`](../interfaces/i_zenoh_client.md#get-address)
    - [`set_address`](../interfaces/i_zenoh_client.md#set-address)
    - [`get_port`](../interfaces/i_zenoh_client.md#get-port)
    - [`set_port`](../interfaces/i_zenoh_client.md#set-port)
    - [`get_session_ptr`](../interfaces/i_zenoh_client.md#get-session-pointer)
    - [`get_config_ptr`](../interfaces/i_zenoh_client.md#get-config-pointer)
    - [`put`](../interfaces/i_zenoh_client.md#put)
    - [`convert_to_zenoh_bytes`](../interfaces/i_zenoh_client.md#convert-to-zenoh-bytes)
