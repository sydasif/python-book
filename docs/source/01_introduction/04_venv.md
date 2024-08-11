## Python Virtual Environments

A Python virtual environment allows you to install third-party packages for testing without affecting your system's Python installation. Here are two common methods to create Python virtual environments:

- The built-in `venv` module
- The `virtualenv` package

### Python’s venv Library

To use the `venv` module, you can run Python with the `-m` flag, which tells Python to run the specified module. Open a command prompt on Windows or a terminal on macOS or Linux, and type the following:

```shell
python -m venv test
```

This command creates a folder named `test` in your current directory. To activate the virtual environment, navigate to the `test` folder and run this command on Linux/macOS:

```shell
source bin/activate 
```

You can now install new packages in your virtual environment without affecting your system. When you're done, deactivate the virtual environment by running the `deactivate` command.

### The virtualenv Package

The `virtualenv` package was the original method for creating Python virtual environments. It has some advantages over the `venv` module:

- It's faster.
- It can create virtual environments for multiple Python versions.
- It can be upgraded via `pip`.

To install `virtualenv`, use `pip`:

```shell
pip install virtualenv
```

Once installed, create a virtual environment with this command:

```shell
virtualenv <FOLDER_NAME>
```

#### Virtual Environment for a Specific Version

To create a virtual environment for a specific Python version, use:

```shell
virtualenv -p python3.7 venv
```

This command won't work with the `venv` module. Activating, deactivating, and freezing work the same way as with the `venv` module.

### Pin Your Dependencies

To make your virtual environments reproducible, you can create a `requirements.txt` file while your virtual environment is active:

```shell
python -m pip freeze > requirements.txt
```

After working or deleting your `venv` folder, recreate the same environment with the `requirements.txt` file:

```shell
virtualenv new-venv
source new-venv/bin/activate
python -m pip install -r requirements.txt
```

For more information, check out these resources:

- [Python Virtual Environments: A Primer](https://realpython.com/python-virtual-environments-a-primer/)
- [Set Up a Local Programming Environment on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-local-programming-environment-on-ubuntu-20-04)
