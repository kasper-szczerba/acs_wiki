# Pixel Unpack Buffer

- **Class**: `pixel_unpack_buffer`
- **Namespace**: `acs::opengl`
- **Include**: `#include "opengl/pixel_unpack_buffer.h"`

## Overview

OpenGL Pixel Unpack Buffer (PBO) helper for efficient CUDA-to-OpenGL transfer workflows. It manages PBO allocation, CUDA graphics registration, and texture upload orchestration.

## API

### Public Methods
#### Generate

```cpp
static void generate(unsigned int& buffer_id, int width, int height, cudaGraphicsResource_t* cuda_pbo_resource);
```
Creates and initializes a pixel unpack buffer sized for the specified frame dimensions, and registers it with CUDA.

##### Parameters
- `buffer_id` (`unsigned int&`): Output OpenGL buffer object ID for the generated PBO.
- `width` (`int`): Target frame width in pixels.
- `height` (`int`): Target frame height in pixels.
- `cuda_pbo_resource` (`cudaGraphicsResource_t*`): Output CUDA graphics resource handle associated with the generated PBO.
#### Bind

```cpp
static void bind(unsigned int buffer_id);
```
Binds the pixel unpack buffer to `GL_PIXEL_UNPACK_BUFFER` for subsequent upload operations.

##### Parameters
- `buffer_id` (`unsigned int`): OpenGL buffer object ID of the PBO to bind.
#### Unbind

```cpp
static void unbind();
```
Unbinds the current pixel unpack buffer from `GL_PIXEL_UNPACK_BUFFER`.
#### Free

```cpp
static void free(unsigned int& buffer_id, cudaGraphicsResource_t* cuda_pbo_resource);
```
Releases the pixel unpack buffer and any associated OpenGL resources.

##### Parameters
- `buffer_id` (`unsigned int&`): OpenGL buffer object ID of the PBO to release.
- `cuda_pbo_resource` (`cudaGraphicsResource_t*`): CUDA graphics resource handle associated with the PBO to unregister and release.
#### Resize

```cpp
static void resize(unsigned int& buffer_id, int width, int height, cudaGraphicsResource_t* cuda_pbo_resource);
```
Reallocates the pixel unpack buffer for new dimensions and refreshes CUDA registration state.

##### Parameters
- `buffer_id` (`unsigned int&`): OpenGL buffer object ID of the PBO to resize.
- `width` (`int`): New target frame width in pixels.
- `height` (`int`): New target frame height in pixels.
- `cuda_pbo_resource` (`cudaGraphicsResource_t*`): CUDA graphics resource handle to update/re-register for the resized PBO.
#### To OpenGL Texture

```cpp
static void to_opengl_texture(unsigned int buffer_id,
                              unsigned int texture_id,
                              int width,
                              int height,
                              size_t src_pitch,
                              cudaGraphicsResource_t* cuda_pbo_resource,
                              const void* data);
```
Copies source image data through the PBO path and updates the target OpenGL texture.

##### Parameters
- `buffer_id` (`unsigned int`): OpenGL buffer object ID of the PBO used as transfer staging memory.
- `texture_id` (`unsigned int`): OpenGL texture object ID that receives the uploaded pixel data.
- `width` (`int`): Image width in pixels.
- `height` (`int`): Image height in pixels.
- `src_pitch` (`size_t`): Source row stride in bytes.
- `cuda_pbo_resource` (`cudaGraphicsResource_t*`): CUDA graphics resource handle bound to the target PBO.
- `data` (`const void*`): Pointer to source pixel data to upload.
