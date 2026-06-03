# Dnn Model

- **Class**: `dnn_model`
- **Namespace**: `acs::vision`
- **Include**: `#include "vision/utility/dnn_model.h"`

## Overview

Utility wrapper for OpenCV DNN inference used by perception components to run model forward passes on CPU/GPU-backed image tensors.

## API

### Constructors
#### Constructor

```cpp
explicit dnn_model(const parameters_t& parameters);
```
Creates a DNN model wrapper from the provided model/runtime configuration.

##### Parameters
- `parameters` (`const parameters_t&`): DNN model configuration bundle (network paths, input shape, and preprocessing options).

### Nested Types

#### Structs
##### Parameters T

```cpp
struct parameters_t {
  std::string model_path;
  std::string config_path;
  int input_width;
  int input_height;
  float scale_factor;
  cv::Scalar mean;
  bool swap_rb;
  bool crop;
};
```
DNN model configuration values used to load the network and preprocess inputs.

- `model_path` (`std::string`): Path to the model weights file.
- `config_path` (`std::string`): Path to the model configuration/prototxt file when required by the backend.
- `input_width` (`int`): Model input width in pixels.
- `input_height` (`int`): Model input height in pixels.
- `scale_factor` (`float`): Scalar multiplier applied during blob preprocessing.
- `mean` (`cv::Scalar`): Per-channel mean values subtracted during input normalization.
- `swap_rb` (`bool`): Swaps red/blue channels during preprocessing when true.
- `crop` (`bool`): Crops the resized image during blob creation when true.

### Public Methods
#### Forward

```cpp
[[nodiscard]] cv::Mat forward(const cv::Mat& input);
```
Runs a forward inference pass and returns model output activations for the provided input tensor.

##### Parameters
- `input` (`const cv::Mat&`): Input image tensor (CPU or CUDA-backed) to preprocess and feed into the model.
#### Forward

```cpp
[[nodiscard]] cv::Mat forward(const cv::cuda::GpuMat& input);
```
Runs a forward inference pass and returns model output activations for the provided input tensor.

##### Parameters
- `input` (`const cv::cuda::GpuMat&`): Input image tensor (CPU or CUDA-backed) to preprocess and feed into the model.
