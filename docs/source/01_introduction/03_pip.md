## What is Python pip?

`pip` is the package installer for Python. You can use `pip` to install packages from the Python Package Index and other repositories.

## Installation

Usually, `pip` is automatically installed if you are:

- Working in a virtual environment
- Using Python downloaded from python.org
- Using Python that has not been modified by a redistributor to remove `ensurepip`

### Supported Methods

If your Python environment does not have `pip` installed, there are two mechanisms supported directly by pip’s maintainers:

- **ensurepip**: Python comes with an `ensurepip` module that can install `pip` in a Python environment.
- **get-pip.py**: This is a Python script that uses some bootstrapping logic to install `pip`. You can download the script from the [official site](https://bootstrap.pypa.io/get-pip.py) and run it.

### Alternative Methods

Depending on how you installed Python, there might be other mechanisms available for installing `pip`, such as using [Linux package managers](https://packaging.python.org/en/latest/guides/installing-using-linux-tools/#installing-pip-setuptools-wheel-with-linux-package-managers).

#### Debian/Ubuntu

On Ubuntu, `pip` often comes pre-installed. If not, you can install it with the following commands:

```shell
sudo apt update
sudo apt install python3-venv python3-pip
```

To check installed modules via `pip`, use `pip list`, and to check the `pip` version, use `pip --version`.

## Installing Modules with pip

Python has an active community of contributors and users who make their software available for others to use under open-source license terms. `pip` is the preferred installer program and is included by default with Python binary installers starting from Python 3.4.

### Basic Usage

The following command will install the latest version of a module and its dependencies from the Python Packaging Index:

```shell
python3 -m pip install netmiko
```

You can also specify an exact or minimum version directly on the command line:

```shell
python -m pip install SomePackage==1.0.4    # specific version
```

### Upgrading Existing Modules

To upgrade existing modules, use:

```shell
python3 -m pip install --upgrade netmiko
```

To upgrade `pip` itself, use:

```shell
python3 -m pip install -U pip
```

These steps should help you get started with `pip` and managing Python packages effectively.
