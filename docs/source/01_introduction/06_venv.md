# Python Virtual Environments

A Python virtual environment is a setting where you can install 3rd party packages for testing without affecting the system Python installation. There are several different ways to create Python virtual environments. We will focus on the following two methods:

- The built-in `venv` module
- The `virtualenv` package

## [Python’s venv Library](https://docs.python.org/3/library/venv.html)

To use `venv` module, you can run Python using the `-m` flag. The `-m` flag tells Python to run the specified module that follows by `-m`. Open up a `cmd.exe` on Windows or a terminal on Mac or Linux. Then type the following:

```console
[$] <> python -m venv test
```

This will create a folder named *test* in whatever directory that you are open to in your terminal session. To activate the virtual environment, you will need to change directories into the test folder and run this on Linux/MacOS:

```console
[$] <> source bin/activate 
```

You can now install new packages and they will install in your virtual environment instead of your system. When you are finished, you can deactivate the virtual environment by running the `deactivate` command in the terminal.

## [The virtualenv Package](https://pypi.org/project/virtualenv/)

The `virtualenv` package was the original method for creating Python virtual environments. The `virtualenv` package is better than `venv` library in the following ways:

- It’s faster  
- Can create virtual environments for multiple versions
- Can be upgraded via `pip`

You can install `virtualenv` by using `pip`:

```console
[$] <> pip install virtualenv 
```

Once installed, you can create a virtual environment using your terminal or `cmd.exe` like this:

```console
[$] <> virtualenv <FOLDER_NAME>
```

### Virtual environment for a specific version

To create virtual environment for a specific version environment use the below command:

```console
[$] <> virtualenv -p python3.7 venv
```

This will not work in a virtual environment using Python’s `venv` module. Activating, deactivating and freezing, work exactly as a virtual environment using Python’s `venv` module.

## Pin Your Dependencies

To make your virtual environments reproducible, you may need its contents. To do this is by creating `requirements.txt` file while your virtual environment is active.

```console
[$] <> python -m pip freeze > requirements.txt
```

After working/deleting your `venv` folder you can create the same environment with the `requirements.txt` file.

```console
[$] <> virtualenv new-venv
$ source new-venv/bin/activate
$ python -m pip install -r requirements.txt
```

```{seealso}
- [Python Virtual Environments: A Primer](https://realpython.com/python-virtual-environments-a-primer/)
- [Set Up a Local Programming Environment on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-local-programming-environment-on-ubuntu-20-04)
```
