# Texture

- **Class**: `texture`
- **Namespace**: `acs::opengl`
- **Include**: `#include "opengl/texture.h"`

## Overview

OpenGL texture helper for allocating, resizing, and updating 2D texture storage used by rendering and visualization pipelines.

## API

### Public Methods
#### Generate

```cpp
static void generate(unsigned int& texture_id, int width, int height);
```
Creates a 2D OpenGL texture object and allocates storage for the specified dimensions.

##### Parameters
- `texture_id` (`unsigned int&`): Output OpenGL texture object ID for the generated texture.
- `width` (`int`): Initial texture width in pixels.
- `height` (`int`): Initial texture height in pixels.
#### Allocate

```cpp
static void allocate(unsigned int texture_id, int width, int height);
```
Allocates or reallocates texture storage for an existing texture object.

##### Parameters
- `texture_id` (`unsigned int`): OpenGL texture object ID to allocate.
- `width` (`int`): Texture width in pixels.
- `height` (`int`): Texture height in pixels.
#### Bind

```cpp
static void bind(unsigned int texture_id);
```
Binds the texture for subsequent OpenGL operations on the current context.

##### Parameters
- `texture_id` (`unsigned int`): OpenGL texture object ID to bind.
#### Unbind

```cpp
static void unbind();
```
Unbinds the current texture from the active texture target.
#### Free

```cpp
static void free(unsigned int& texture_id);
```
Deletes the texture object and releases its GPU memory allocation.

##### Parameters
- `texture_id` (`unsigned int&`): OpenGL texture object ID to delete.
#### Resize

```cpp
static void resize(unsigned int texture_id, int width, int height);
```
Resizes texture storage to match new frame dimensions.

##### Parameters
- `texture_id` (`unsigned int`): OpenGL texture object ID to resize.
- `width` (`int`): New texture width in pixels.
- `height` (`int`): New texture height in pixels.
#### Update From Pbo

```cpp
static void update_from_pbo(unsigned int texture_id, int width, int height);
```
Updates texture contents from the currently bound pixel unpack buffer.

##### Parameters
- `texture_id` (`unsigned int`): OpenGL texture object ID to update.
- `width` (`int`): Texture width in pixels.
- `height` (`int`): Texture height in pixels.
#### Update

```cpp
static void update(unsigned int texture_id, int width, int height, const void* data);
```
Uploads raw pixel data directly into the texture storage.

##### Parameters
- `texture_id` (`unsigned int`): OpenGL texture object ID to update.
- `width` (`int`): Image width in pixels.
- `height` (`int`): Image height in pixels.
- `data` (`const void*`): Pointer to source pixel data to upload.
