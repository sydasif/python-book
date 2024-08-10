# [What is a pip?](https://pypi.org/project/pip/)

`pip` is the package installer for Python. You can use `pip` to install packages from the Python Package Index and other indexes/libraries.

## [Installation](https://pip.pypa.io/en/stable/installation/)

Usually, `pip` is automatically installed if you are:

- working in a virtual environment
- using Python downloaded from python.org
- using Python that has not been modified by a redistributor to remove `ensurepip`

### Supported methods

If your Python environment does not have `pip` installed, there are '2' mechanisms to install `pip` supported directly by pip’s maintainers:

- ensurepip
- get-pip.py

### Alternative methods

Depending on how you installed Python, there might be other mechanisms available to you for installing `pip` such as using [Linux package managers](https://packaging.python.org/en/latest/guides/installing-using-linux-tools/#installing-pip-setuptools-wheel-with-linux-package-managers).

#### [Debian/Ubuntu](https://packaging.python.org/en/latest/guides/installing-using-linux-tools/#id7)

On Ubuntu its come pre-installed if not, install it with the below command:

```shell
[$] <> sudo apt update
$ sudo apt install python3-venv python3-pip
```

To check to install modules via `pip` use `pip list` and to check `pip` version use `pip --version` commands.

## [Installing Modules with pip](https://docs.python.org/3.8/installing/index.html)

As a popular open-source development project, Python has an active supporting community of contributors and users that also make their software available for other Python developers to use under open-source license terms. `pip` is the preferred installer program. Starting with Python 3.4 is included by default with the Python binary installers.

### Basic usage

The following command will install the latest version of a module and its dependencies from the Python Packaging Index.

```shell
[$] <> python3 -m pip install netmiko
```

It is also possible to specify an exact or minimum version directly on the command line, the package name and the version.

```shell
[$] <> python -m pip install SomePackage==1.0.4    # specific version
```

Upgrading existing modules

```shell
[$] <> python3 -m pip install --upgrade netmiko
```

or `pip` must be requested explicitly to upgrade.

```shell
[$] <> python3 -m pip install -U pip
```
