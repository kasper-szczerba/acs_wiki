# Gps Interface

- **Interface**: `i_gps`
- **Namespace**: `acs::utility`
- **Include**: `#include "utility/interfaces/i_gps.h"`

## Overview

Interface for reading GPS receiver data, parsing supported message formats, and exposing the latest position fix and conversion helpers.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    i_gps["i_gps"]
    i_gps["i_gps"] --> i_object["i_object"]
```

### Derived Diagram

```mermaid
graph LR
    i_gps["i_gps"]
    i_gps["i_gps"] --> gps["gps"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`i_gps`](i_gps.md)
  - [`i_object`](../../core/interfaces/i_object.md)

### Derived Hierarchy

- [`i_gps`](i_gps.md)
  - [`gps`](../implementations/gps.md)

## API

### Public Methods
#### Parse Nmea

```cpp
virtual void parse_nmea(std::string_view sentence) = 0;
```
Parses a single NMEA sentence from the GPS receiver stream.

##### Parameters
- `sentence` (`std::string_view`): NMEA sentence to parse.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Parse Ubx

```cpp
virtual void parse_ubx(const std::vector<uint8_t>& buffer) = 0;
```
Parses a UBX binary frame from the GPS receiver stream.

##### Parameters
- `buffer` (`const std::vector<uint8_t>&`): Raw UBX payload bytes to parse.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Get Latest Point

```cpp
[[nodiscard]] virtual gps_point get_latest_point() const = 0;
```
Returns the most recently parsed GPS point.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Convert To Utm

```cpp
[[nodiscard]] virtual cv::Vec2d convert_to_utm(double lat, double lon) const = 0;
```
Converts the provided latitude and longitude to UTM coordinates.

##### Parameters
- `lat` (`double`): Latitude in decimal degrees.
- `lon` (`double`): Longitude in decimal degrees.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Load Reference Points

```cpp
[[nodiscard]] virtual std::vector<gps_point> load_reference_points(std::string_view file_path) const = 0;
```
Loads a list of reference GPS points from a file.

##### Parameters
- `file_path` (`std::string_view`): Path to the reference-point file to load.

!!! note
    Pure virtual method, must be implemented by derived classes.
#### Read Point

```cpp
[[nodiscard]] virtual gps_point read_point(int index, std::string_view file_path) const = 0;
```
Reads a single GPS point by index from a file.

##### Parameters
- `index` (`int`): Zero-based point index to read.
- `file_path` (`std::string_view`): Path to the GPS point file to read from.

!!! note
    Pure virtual method, must be implemented by derived classes.
