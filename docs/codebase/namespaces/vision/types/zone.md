# Zone

- **Namespace**: `acs::vision`
- **Include**: `#include "vision/types/zone.h"`

## Overview

Zone classification types used by obstacle analysis to summarize free/occupied state in left, center, and right road regions.

## API

### Public Structs
#### Zone Result

```cpp
struct zone_result {
    cv::Rect bounding_box;
    bool has_obstacle = false;
  }
```

- `bounding_box` (`cv::Rect`): The bounding box.
- `has_obstacle` (`bool`): The has obstacle.

### Public Enums
#### Road Zone

```cpp
enum class road_zone : uint8_t {
    left,
    center,
    right,
    none
  }
```

Values:
- `left`: The left.
- `center`: The center.
- `right`: The right.
- `none`: The none.
