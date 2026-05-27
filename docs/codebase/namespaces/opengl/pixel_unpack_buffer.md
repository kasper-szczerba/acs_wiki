# Pixel Unpack Buffer

- **Class**: `pixel_unpack_buffer`
- **Namespace**: `acs::opengl`
- **Include**: `#include "opengl/pixel_unpack_buffer.h"`

## Overview

Pixel Unpack Buffer.

## API

### Public Methods
#### Generate

```cpp
static void generate(unsigned int& buffer_id, int width, int height, cudaGraphicsResource_t* cuda_pbo_resource);
```

##### Parameters
- `buffer_id`: The buffer ID.
- `width`: The width.
- `height`: The height.
- `cuda_pbo_resource`: The cuda pbo resource.
#### Bind

```cpp
static void bind(unsigned int buffer_id);
```

##### Parameters
- `buffer_id`: The buffer ID.
#### Unbind

```cpp
static void unbind();
```

#### Free

```cpp
static void free(unsigned int buffer_id);
```
Releases the parsed configuration data.

##### Parameters
- `buffer_id`: The buffer ID.
#### Resize

```cpp
static void resize(unsigned int& buffer_id, int width, int height, cudaGraphicsResource_t* cuda_pbo_resource);
```

##### Parameters
- `buffer_id`: The buffer ID.
- `width`: The width.
- `height`: The height.
- `cuda_pbo_resource`: The cuda pbo resource.
#### To Opengl Texture

```cpp
static void to_opengl_texture(unsigned int buffer_id,
                              unsigned int texture_id,
                              int width,
                              int height,
                              size_t src_pitch,
                              cudaGraphicsResource_t* cuda_pbo_resource,
                              const void* data);
```

##### Parameters
- `buffer_id`: The buffer ID.
- `texture_id`: The texture ID.
- `width`: The width.
- `height`: The height.
- `src_pitch`: The src pitch.
- `cuda_pbo_resource`: The cuda pbo resource.
- `data`: The data.
