# Python Virtual Environments

A Python virtual environment is an environment where you can install 3rd party packages for testing without affecting the system Python installation. There are several different ways to create Python virtual environments. We will focus on the following two methods:

• The built-in venv module

• The virtualenv package

## [Python’s venv Library](https://docs.python.org/3/library/venv.html)

To use venv, you can run Python using the -m flag. The -m flag tells Python to run the specified module that follows -m. Open up a cmd.exe on Windows or a terminal in Mac or Linux. Then type the following:

```console
python -m venv test
```

This will create a folder named test in whatever directory that you are open to in your terminal session. To activate the virtual environment, you will need to change directories into the test folder and run this on Linux/Mac:

```console
source bin/activate 
```

You can now install new packages and they will install in your virtual environment instead of your system. When you are finished, you can deactivate the virtual environment by running `deactivate` command in the terminal.

## [The virtualenv Package](https://pypi.org/project/virtualenv/)

The virtualenv package was the original method for creating Python virtual environments. The actual virtualenv package is better than venv in the following ways:

• It’s faster  
• Can create virtual environments for multiple Python versions
• Can be upgraded via pip

You can install virtualenv by using pip:

```console
pip install virtualenv 
```

Once installed, you can create a virtual environment using your terminal or cmd.exe like this:

```console
virtualenv <FOLDER_NAME>
```

### Pin Your Dependencies

To make your virtual environments reproducible, you may need its contents. To do this is by creating _requirements.txt_ file while your virtual environment is active.

`python -m pip freeze > requirements.txt`

After working/deleting your _venv_ folder you can create same environment with requirements.txt file.

```console
virtualenv new-venv
source new-venv/bin/activate
python -m pip install -r requirements.txt
```

### Creating virtual environment for specific version

To create a specific version environment use below command:

`virtualenv -p python3.7 venv`

This will not work in virtual environment using Python’s _venv_ module.

Activating, deactivating and freezing, works exactly as virtual environment using Python’s _venv_ module.

```{seealso}
[Python Virtual Environments: A Primer](https://realpython.com/python-virtual-environments-a-primer/)
```
