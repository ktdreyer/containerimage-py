![containerimage-py](./doc/images/container-image-py.png)

# containerimage-py

A python library for interacting with container images and container image registries

## Quick Example

Here is a quick motivating example for how you might use `containerimage-py` in your python scripts to fetch basic information about a container image.
```python
from image.containerimage import ContainerImage

# Initialize a ContainerImage given a tag reference
my_image = ContainerImage("registry.k8s.io/pause:3.5")

# Display some basic information about the container image
print(
    f"Size of {str(my_image)}: " + \
    my_image.get_size_formatted(auth={}) # 499.91 MB
)
print(
    f"Digest for {str(my_image)}: " + \
    my_image.get_digest(auth={}) # sha256:1ff6c18fbef2045af6b9c16bf034cc421a29027b800e4f9b68ae9b1cb3e9ae07
)
```

To run this example, simply execute the following from the root of this repository
```sh
python3 examples/quick-example.py
```

## Installation

### Using Pip

> IMPORTANT: This project has not yet been released on PyPi.  This will not work at this point in time.  Instead follow [the local install instructions](#installation).

Run the following command to install the latest version of this package

```
pip install containerimage-py
```

### Local Install

1. Clone this repository
2. [Build the project from source](#build)
3. Locate the `.whl` (wheel) file in the `dist` folder
    - It should be named something like so: `containerimage_py-0.1.0-py3-none-any.whl`
4. Run the following command from the root of the repository, replacing the name of the `.whl` file if necessary
    ```
    pip install dist/containerimage_py-0.1.0-py3-none-any.whl
    ```

## Build

From the root of this repository, execute
```sh
make build
```

Under the hood, this will execute `python3 -m build` and produce a `.whl` (wheel) and `.tgz` (TAR-GZip archive) file in the `dist` subdirectory.
