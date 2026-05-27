# Matrix Converter

- **Class**: `matrix_converter`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/utility/matrix_converter.h"`

## Overview

Matrix Converter.

## API

### Public Methods
#### Convert Color To GPU Mat

```cpp
[[nodiscard]] static cv::cuda::GpuMat convert_color_to_gpu_mat(const sl::Mat &input);
```

##### Parameters
- `input`: The input.
#### Convert Depth To GPU Mat

```cpp
[[nodiscard]] static cv::cuda::GpuMat convert_depth_to_gpu_mat(const sl::Mat &input);
```

##### Parameters
- `input`: The input.
