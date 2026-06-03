# Traffic Light Detector

- **Class**: `traffic_light_detector`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/implementations/traffic_light_detector.h"`

## Overview

Concrete `i_traffic_light_detector` implementation that analyzes camera imagery with a DNN model and obstacle context to determine red-light state.

## Inheritance Diagram

### Base Diagram

```mermaid
graph LR
    traffic_light_detector["traffic_light_detector"]
    i_threaded_object["i_threaded_object"] --> i_object["i_object"]
    i_traffic_light_detector["i_traffic_light_detector"] --> i_threaded_object["i_threaded_object"]
    object["object"] --> i_object["i_object"]
    threaded_object["threaded_object"] --> i_threaded_object["i_threaded_object"]
    threaded_object["threaded_object"] --> object["object"]
    traffic_light_detector["traffic_light_detector"] --> i_traffic_light_detector["i_traffic_light_detector"]
    traffic_light_detector["traffic_light_detector"] --> threaded_object["threaded_object"]
```

## Inheritance Hierarchy

### Base Hierarchy

- [`traffic_light_detector`](traffic_light_detector.md)
  - [`i_traffic_light_detector`](../interfaces/i_traffic_light_detector.md)
    - [`i_threaded_object`](../../core/interfaces/i_threaded_object.md)
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
traffic_light_detector(float update_rate,
                       const parameters_t& parameters,
                       std::shared_ptr<i_camera> camera,
                       std::shared_ptr<i_obstacle_detector> obstacle_detector);
```
Creates a traffic-light detector with update cadence, model configuration, and shared perception dependencies.

##### Parameters
- `update_rate` (`float`): Requested detection frequency in Hz for traffic-light inference.
- `parameters` (`const parameters_t&`): Traffic-light detector configuration bundle (model settings and decision thresholds).
- `camera` (`std::shared_ptr<i_camera>`): Shared camera dependency that provides live frames for traffic-light analysis.
- `obstacle_detector` (`std::shared_ptr<i_obstacle_detector>`): Shared obstacle-detector dependency used for scene context and candidate filtering.

### Nested Types

#### Structs
##### Parameters T

```cpp
struct parameters_t {
  dnn_model::parameters_t model_params;
  float confidence_threshold;
  int red_light_class_id;
  float distance_threshold;
  int on_threshold;
  int off_threshold;
};
```
Traffic-light detection settings used during model inference and state debouncing.

- `model_params` (`dnn_model::parameters_t`): DNN model configuration used to load and run traffic-light inference.
- `confidence_threshold` (`float`): Minimum detection confidence required to accept a traffic-light prediction.
- `red_light_class_id` (`int`): Model class ID interpreted as a red traffic light.
- `distance_threshold` (`float`): Maximum scene distance in meters considered for red-light candidates.
- `on_threshold` (`int`): Consecutive positive detections required to switch state to red-light active.
- `off_threshold` (`int`): Consecutive negative detections required to clear the red-light active state.

### Public Methods

#### Implementations
- [`i_traffic_light_detector`](../interfaces/i_traffic_light_detector.md)
    - [`is_red_light_detected`](../interfaces/i_traffic_light_detector.md#is-red-light-detected)

### Protected Methods
#### Update

```cpp
void update() override;
```
Runs one traffic-light detection cycle and updates cached red-light state.
