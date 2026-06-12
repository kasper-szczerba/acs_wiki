# Navigation Manager

- **Class**: `navigation_manager`
- **Namespace**: `acs::logic`
- **Include**: `#include "logic/navigation_manager.h"`

## Overview

Navigation manager that consumes GPS/state data, tracks route geometry, and produces steering preview/command outputs for higher-level control logic.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    navigation_manager["navigation_manager"]
    navigation_manager["navigation_manager"] --> object["object"]
    object["object"] --> i_object["i_object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`navigation_manager`](navigation_manager.md)
  - [`object`](../core/implementations/object.md)
    - [`i_object`](../core/interfaces/i_object.md)

## API

### Constructors
#### Constructor

```cpp
navigation_manager(std::shared_ptr<utility::i_gps> gps_ptr, const parameters_t& parameters);
```
Creates a navigation manager with GPS dependency and route/steering parameters.

##### Parameters
- `gps_ptr` (`std::shared_ptr<utility::i_gps>`): Shared GPS dependency that provides current position/heading inputs.
- `parameters` (`const parameters_t&`): Navigation configuration bundle including track source and pure-pursuit tuning values.

### Nested Types

#### Enums
##### Track Object Kind

```cpp
enum class track_object_kind {
  stop_sign,
  crosswalk,
  traffic_light,
  unknown,
};
```
Classifies semantic objects associated with a route track.

###### Values
- `stop_sign`: Stop-sign marker.
- `crosswalk`: Crosswalk marker.
- `traffic_light`: Traffic-light marker.
- `unknown`: Unknown or unclassified marker.

#### Structs
##### Track Object T

```cpp
struct track_object_t {
  int id;
  track_object_kind kind;
  std::string type_name;
  std::string section;
  cv::Vec2d position;
};
```
Track-annotated object metadata used for route context.

- `id` (`int`): Stable object identifier.
- `kind` (`track_object_kind`): Semantic object kind.
- `type_name` (`std::string`): Source-provided object type label.
- `section` (`std::string`): Route section label associated with the object.
- `position` (`cv::Vec2d`): Object position in map/projected coordinates.
##### Parameters T

```cpp
struct parameters_t {
  std::string_view track_file;
  double lookahead_distance;
  double wheelbase;
  double steering_gain;
};
```
Navigation configuration values for route following and steering preview.

- `track_file` (`std::string_view`): Path to the route/track file to load.
- `lookahead_distance` (`double`): Forward lookahead distance in meters used by steering logic.
- `wheelbase` (`double`): Vehicle wheelbase in meters used for curvature-to-angle conversion.
- `steering_gain` (`double`): Gain applied to steering response.
##### Preview T

```cpp
struct preview_t {
  bool has_track;
  bool has_steering_solution;
  cv::Vec2d current_position;
  cv::Vec2d closest_point;
  cv::Vec2d lookahead_point;
  double heading_rad;
  double steering_angle_deg;
  double cross_track_error_m;
  int steering_command;
  std::vector<cv::Vec2d> reference_track;
  std::vector<track_object_t> track_objects;
};
```
Navigation preview snapshot used by debug/visualization components.

- `has_track` (`bool`): Indicates whether a valid reference track is loaded.
- `has_steering_solution` (`bool`): Indicates whether a valid steering solution was computed.
- `current_position` (`cv::Vec2d`): Current vehicle position in map/projected coordinates.
- `closest_point` (`cv::Vec2d`): Nearest point on the reference track.
- `lookahead_point` (`cv::Vec2d`): Selected lookahead target point on the reference track.
- `heading_rad` (`double`): Current heading angle in radians.
- `steering_angle_deg` (`double`): Computed steering angle in degrees.
- `cross_track_error_m` (`double`): Lateral cross-track error in meters.
- `steering_command` (`int`): Computed actuator steering command.
- `reference_track` (`std::vector<cv::Vec2d>`): Reference track points used by navigation logic.
- `track_objects` (`std::vector<track_object_t>`): Track-associated semantic objects used for context.

### Public Methods
#### Compute Steering Command

```cpp
[[nodiscard]] int compute_steering_command(const cv::Vec2d& current_position);
```
Computes a steering command from the current position using configured route-following logic.

##### Parameters
- `current_position` (`const cv::Vec2d&`): Current vehicle position in map/projected coordinates.
#### Get Preview

```cpp
[[nodiscard]] preview_t get_preview() const;
```
Returns the latest navigation preview snapshot including selected points and steering diagnostics.
#### Has Track

```cpp
[[nodiscard]] bool has_track() const;
```
Returns whether a valid reference track is currently loaded.
#### Reset History

```cpp
void reset_history();
```
Clears cached navigation history and intermediate preview state.
