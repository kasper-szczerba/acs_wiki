# Steering Handler

- **Class**: `steering_handler`
- **Namespace**: `acs::logic`
- **Include**: `#include "logic/steering_handler.h"`

## Overview

Steering computation helper that applies pure-pursuit geometry and command-range mapping to produce steering outputs from track data.

## API

### Constructors
#### Constructor

```cpp
explicit steering_handler(const parameters_t& parameters);
```
Creates a steering handler with vehicle geometry and steering-command range parameters.

##### Parameters
- `parameters` (`const parameters_t&`): Steering-handler configuration bundle used for pure-pursuit and actuator mapping.

### Nested Types

#### Structs
##### Parameters T

```cpp
struct parameters_t {
  double wheelbase;
  double steering_gain;
  double min_steering_deg;
  double max_steering_deg;
  int min_steering_cmd;
  int max_steering_cmd;
};
```
Steering-handler configuration values.

- `wheelbase` (`double`): Vehicle wheelbase in meters used for steering geometry.
- `steering_gain` (`double`): Gain applied to steering response.
- `min_steering_deg` (`double`): Minimum steering angle in degrees.
- `max_steering_deg` (`double`): Maximum steering angle in degrees.
- `min_steering_cmd` (`int`): Minimum actuator steering command value.
- `max_steering_cmd` (`int`): Maximum actuator steering command value.
##### Result T

```cpp
struct result_t {
  bool valid;
  int steering_command;
  double steering_angle_deg;
  double cross_track_error_m;
  cv::Vec2d closest_point;
  cv::Vec2d lookahead_point;
};
```
Pure-pursuit computation output values.

- `valid` (`bool`): Indicates whether a valid steering solution was computed.
- `steering_command` (`int`): Computed actuator steering command.
- `steering_angle_deg` (`double`): Computed steering angle in degrees.
- `cross_track_error_m` (`double`): Lateral cross-track error in meters.
- `closest_point` (`cv::Vec2d`): Nearest point on the reference track.
- `lookahead_point` (`cv::Vec2d`): Selected lookahead target point on the reference track.

### Public Methods
#### Compute Pure Pursuit

```cpp
[[nodiscard]] result_t compute_pure_pursuit(const cv::Vec2d& current_position,
                                            double heading_rad,
                                            const std::vector<cv::Vec2d>& reference_track,
                                            double lookahead_distance_m) const;
```
Computes pure-pursuit steering outputs for the current position and heading against a reference track.

##### Parameters
- `current_position` (`const cv::Vec2d&`): Current vehicle position in map/projected coordinates.
- `heading_rad` (`double`): Current vehicle heading in radians.
- `reference_track` (`const std::vector<cv::Vec2d>&`): Reference trajectory points to follow.
- `lookahead_distance_m` (`double`): Forward lookahead distance in meters used to select the target point.
