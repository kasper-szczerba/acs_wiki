# Texture

- **Class**: `texture`
- **Namespace**: `acs::opengl`
- **Include**: `#include "opengl/texture.h"`

## Overview

Texture.

## API

### Public Methods
#### Generate

```cpp
static void generate(unsigned int& texture_id, int width, int height);
```

##### Parameters
- `texture_id`: The texture ID.
- `width`: The width.
- `height`: The height.
#### Allocate

```cpp
static void allocate(unsigned int texture_id, int width, int height);
```

##### Parameters
- `texture_id`: The texture ID.
- `width`: The width.
- `height`: The height.
#### Bind

```cpp
static void bind(unsigned int texture_id);
```

##### Parameters
- `texture_id`: The texture ID.
#### Unbind

```cpp
static void unbind();
```

#### Free

```cpp
static void free(unsigned int texture_id);
```
Releases the parsed configuration data.

##### Parameters
- `texture_id`: The texture ID.
#### Resize

```cpp
static void resize(unsigned int texture_id, int width, int height);
```

##### Parameters
- `texture_id`: The texture ID.
- `width`: The width.
- `height`: The height.
#### Update From Pbo

```cpp
static void update_from_pbo(unsigned int texture_id, int width, int height);
```

##### Parameters
- `texture_id`: The texture ID.
- `width`: The width.
- `height`: The height.
#### Update

```cpp
static void update(unsigned int texture_id, int width, int height, const void* data);
```
Performs one update cycle.

##### Parameters
- `texture_id`: The texture ID.
- `width`: The width.
- `height`: The height.
- `data`: The data.
