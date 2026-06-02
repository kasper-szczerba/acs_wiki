# Gps

- **Class**: `gps`
- **Namespace**: `acs::utility`
- **Include**: `#include "utility/implementations/gps.h"`

## Overview

Concrete `i_gps` implementation that reads NMEA and UBX input from a serial GPS receiver, converts positions for downstream consumers, and exposes the latest parsed fix.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    gps["gps"]
    gps["gps"] --> i_gps["i_gps"]
    gps["gps"] --> threaded_object["threaded_object"]
    i_gps["i_gps"] --> i_object["i_object"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
    object["object"] --> i_object["i_object"]
    threaded_object["threaded_object"] --> i_threaded_object["i_threaded_object"]
    threaded_object["threaded_object"] --> object["object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`gps`](gps.md)
  - [`i_gps`](../interfaces/i_gps.md)
    - [`i_object`](../../core/interfaces/i_object.md)
  - [`threaded_object`](../../core/implementations/threaded_object.md)
    - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
      - [`i_object`](../../core/interfaces/i_object.md)
    - [`object`](../../core/implementations/object.md)
      - [`i_object`](../../core/interfaces/i_object.md)

## API

### Constructors
#### Constructor

```cpp
explicit gps(const parameters_t& params);
```
Creates a GPS reader configured for a serial device and its communication settings.

##### Parameters
- `params` (`const parameters_t&`): GPS reader configuration bundle (serial port name and baud rate).

### Nested Types

#### Structs
##### Parameters T

```cpp
struct parameters_t {
  std::string port_name;
  unsigned int baud_rate;
};
```
GPS reader configuration values used to open the receiver connection.

- `port_name` (`std::string`): Serial port name used to reach the GPS receiver.
- `baud_rate` (`unsigned int`): Serial baud rate used for GPS communication.

### Public Methods

#### Implementations
- [`i_gps`](../interfaces/i_gps.md)
    - [`parse_nmea`](../interfaces/i_gps.md#parse-nmea)
    - [`parse_ubx`](../interfaces/i_gps.md#parse-ubx)
    - [`get_latest_point`](../interfaces/i_gps.md#get-latest-point)
    - [`convert_to_utm`](../interfaces/i_gps.md#convert-to-utm)
    - [`load_reference_points`](../interfaces/i_gps.md#load-reference-points)
    - [`read_point`](../interfaces/i_gps.md#read-point)

### Protected Methods
#### Update

```cpp
void update() override;
```
Performs one update cycle.
