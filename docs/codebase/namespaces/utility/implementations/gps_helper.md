# Gps Helper

- **Class**: `gps_helper`
- **Namespace**: `acs::utility`
- **Include**: `#include "utility/implementations/gps_helper.h"`

## Overview

Concrete `i_gps_helper` implementation that provides reusable geometry and pure-pursuit helper functions for trajectory processing and steering command conversion.

## API

### Public Methods
#### Average Heading

```cpp
[[nodiscard]] static double average_heading(const std::vector<cv::Vec2d>& points);
```
Computes a representative heading angle from a sequence of 2D trajectory points.

##### Parameters
- `points` (`const std::vector<cv::Vec2d>&`): Ordered 2D points used to estimate the aggregate heading direction.
#### Pp Angle To Servo

```cpp
[[nodiscard]] static int pp_angle_to_servo(double degree, double min_deg, double max_deg, int min_cmd, int max_cmd);
```
Maps a steering angle in degrees to a bounded servo command range using configured mechanical limits.

##### Parameters
- `degree` (`double`): Steering angle in degrees to convert to a servo command.
- `min_deg` (`double`): Minimum steering angle supported by the conversion mapping.
- `max_deg` (`double`): Maximum steering angle supported by the conversion mapping.
- `min_cmd` (`int`): Servo command value corresponding to the minimum steering angle.
- `max_cmd` (`int`): Servo command value corresponding to the maximum steering angle.
#### Distance Between Points

```cpp
[[nodiscard]] static double distance_between_points(const cv::Vec2d& p1, const cv::Vec2d& p2);
```
Computes Euclidean distance between two 2D points.

##### Parameters
- `p1` (`const cv::Vec2d&`): First 2D point.
- `p2` (`const cv::Vec2d&`): Second 2D point.
#### Get Closest And Lookahead Points

```cpp
[[nodiscard]] static std::pair<cv::Vec2d, cv::Vec2d> get_closest_and_lookahead_points(const std::vector<cv::Vec2d>& trajectory,
                                                                                      const cv::Vec2d& current_position,
                                                                                      double lookahead_distance);
```
Finds the closest trajectory point to the current position and a forward lookahead target point.

##### Parameters
- `trajectory` (`const std::vector<cv::Vec2d>&`): Reference trajectory points used for nearest/forward target selection.
- `current_position` (`const cv::Vec2d&`): Current vehicle position in the same coordinate frame as the trajectory.
- `lookahead_distance` (`double`): Desired forward distance used when selecting the lookahead point.
#### Offset Track

```cpp
[[nodiscard]] static std::vector<cv::Vec2d> offset_track(const std::vector<cv::Vec2d>& ref_pts,
                                                         double offset_metres,
                                                         double heading_rad);
```
Builds a laterally offset copy of a reference track relative to a heading direction.

##### Parameters
- `ref_pts` (`const std::vector<cv::Vec2d>&`): Reference track points to offset.
- `offset_metres` (`double`): Signed lateral offset distance in meters.
- `heading_rad` (`double`): Reference heading angle in radians used to orient the lateral offset.
