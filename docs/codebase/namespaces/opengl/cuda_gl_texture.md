# Cuda Gl Texture

- **Class**: `cuda_gl_texture`
- **Namespace**: `acs::opengl`
- **Include**: `#include "opengl/cuda_gl_texture.h"`

## Overview

CUDA/OpenGL interop texture helper that owns a texture/PBO pair and provides efficient host/device update paths for rendering workflows.

## API

### Constructors
#### Constructor

```cpp
cuda_gl_texture(int width, int height);
```
Creates a CUDA-GL texture resource with initial dimensions and associated interop buffers.

##### Parameters
- `width` (`int`): Initial texture width in pixels.
- `height` (`int`): Initial texture height in pixels.

### Public Methods
#### Resize

```cpp
void resize(int width, int height);
```
Resizes the underlying texture/PBO resources to new dimensions.

##### Parameters
- `width` (`int`): New texture width in pixels.
- `height` (`int`): New texture height in pixels.
#### Update From Device

```cpp
void update_from_device(const void* device_data, size_t src_pitch);
```
Uploads pixel data from device memory into the OpenGL texture through the CUDA-interoperable PBO path.

##### Parameters
- `device_data` (`const void*`): Pointer to source pixel data in device (GPU) memory.
- `src_pitch` (`size_t`): Source row stride in bytes for the device image buffer.
#### Update From Host

```cpp
void update_from_host(const void* host_data) const;
```
Uploads pixel data from host memory directly into the texture resource.

##### Parameters
- `host_data` (`const void*`): Pointer to source pixel data in host (CPU) memory.
#### Get Texture ID

```cpp
[[nodiscard]] unsigned int get_texture_id() const;
```
Returns the OpenGL texture object ID.
#### Get Pbo ID

```cpp
[[nodiscard]] unsigned int get_pbo_id() const;
```
Returns the OpenGL pixel-buffer object (PBO) ID used for interop transfers.
#### Get Width

```cpp
[[nodiscard]] int get_width() const;
```
Returns the current texture width in pixels.
#### Get Height

```cpp
[[nodiscard]] int get_height() const;
```
Returns the current texture height in pixels.
#### Bind Texture

```cpp
void bind_texture() const;
```
Binds the texture on the current OpenGL context for subsequent operations.
#### Unbind Texture

```cpp
static void unbind_texture();
```
Unbinds the texture from the current OpenGL context.
