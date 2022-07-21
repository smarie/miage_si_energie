# Getting started

*Note: Notepad++ + MarkdownPanel plugin is a good way to visualize and edit this file*

## 1. Installing python

### Windows

Download Miniconda 3.9 installer from [here](https://docs.conda.io/en/latest/miniconda.html).

At the end of the installation, check the boxes "define as de default PYTHON" and "add to PATH"

Checking that the installation was ok:

```bash
> conda env list
# conda environments:
#
base                  *  C:\Miniconda3
```

Now let's check what is the default python interpreter:

```bash
> where python
C:\Users\...\AppData\Local\Microsoft\WindowsApps\python.exe
```

This is not the Miniconda one ! We should activate the base miniconda environment for this:

```bash
> conda activate

(Miniconda) > where python
C:\Miniconda3\python.exe
C:\Users\...\AppData\Local\Microsoft\WindowsApps\python.exe

> python --version
Python 3.7.3
```


### Linux

On Linux targets, conda is not really necessary. 

```bash
> sudo apt update
> sudo apt install python3-pip
> python --version
Python 3.X.y
```

Source: https://linuxize.com/post/how-to-install-pip-on-ubuntu-18.04/#installing-pip-for-python-3

On linux we will use `venv` as a virtual environment manager. This package is available in the standard installation.


### Mac

It seems that the Linux procedure should work on Mac. However here again you may prefer to use conda.


## 2. Creating a virtual enviroment

### Conda

First make sure that no environment is active:

```bash
(Miniconda3) > conda deactivate
>
```

Now let's create an environment with python installed:

```bash
> conda create -n miageTd python=3.8
```

WARNING: each environment needs to be activated before use ! 

```bash
> conda env list
# conda environments:
#
base                  *  C:\Miniconda3
miageTd                  C:\Miniconda3\envs\miageTd

> conda activate miageTd
(miageTd)
```

Now we can check that the python used is the correct one:

```bash
(miageTd) > where python
C:\Miniconda3\envs\baseenv\python.exe
C:\Users\...\AppData\Local\Microsoft\WindowsApps\python.exe
```

You can leave a virtual environment with:

```bash
(miageTd) > conda deactivate
> 
```


### Venv

As opposed to conda, by default `venv` will create the environment in the local folder. So knowing the env name is less important

```bash
> python3 -m venv miageTd
```

Similarly to conda, we have to activate an environment before using it

```bash
> source miageTd/bin/activate
```

Now we can check that the python used is the correct one:

```bash
> which python
.../miageTd/bin/python
```

You can leave a virtual environment with:

```bash
(miageTd) > deactivate
> 
```
