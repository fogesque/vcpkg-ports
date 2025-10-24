# vcpkg-ports

Personal vcpkg overlay ports for custom C++ libraries.

## Prerequisites

- [vcpkg](https://github.com/microsoft/vcpkg) installed and set up
- CMake 3.20 or higher
- C++23 compatible compiler

## Usage

Install any port from this repository using the `--overlay-ports` flag:

```bash
vcpkg install <port-name> --overlay-ports=/path/to/vcpkg-ports
```

For projects using vcpkg manifest mode, add this repository as an overlay in your `vcpkg-configuration.json`:

```json
{
  "overlay-ports": [
    "path/to/vcpkg-ports"
  ]
}
```

Then reference the `<port-name>` in your project's `vcpkg.json`:

```json
{
  "dependencies": [
    "<port-name>"
  ]
}
```

## Available Ports

## errors

**Version:** 1.0.2
**Repository:** [fogesque/errors](https://github.com/fogesque/errors)
**License:** MIT

C++ errors library inspired by Go's error concept. Provides a simple and expressive way to create, wrap, and handle errors in C++ applications.

**Installation:**
```bash
vcpkg install errors --overlay-ports=/path/to/vcpkg-ports
```

**CMake Integration:**
```cmake
find_package(errors CONFIG REQUIRED)
target_link_libraries(your_target PRIVATE errors::errors)
```

**Usage Example:**
```cpp
#include <errors/errors.hpp>

auto err = errors::New("something went wrong");
if (err) {
    // Handle error
}
```

---

## Other Ports Coming Soon

Upcoming libraries to be ported:
* kvalog
* doca-cpp

## Contributing

This is a personal repository for custom vcpkg ports. If you're using these ports and encounter issues, please open an issue in the respective library's repository.
