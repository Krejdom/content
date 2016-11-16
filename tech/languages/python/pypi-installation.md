---
title: PyPI
subsection: python
order: 2
---

# Using pip

If a Python module you need is not packaged for Fedora, you can use pip to install it from [PyPI](https://pypi.python.org/), but you must be a little careful. Installing modules with pip to system directories can lead to unstable system, so make sure you only use pip with the ```--user``` switch, which makes pip install modules to your home directory.

Pip gets installed alongside with Python, so if, for example, you want to install `bokeh` (interactive plots in HTML for Python) from PyPI simply type:

```
$ pip3 install --user bokeh
```

And there you go!

## Using pip in the virtual environment

The best practise is using pip in the virtual environment. It will keep all modules for one project at one place and it will not break your local system. Another advantage is that you can have more versions of the same module in different virtual environments.

Let's install `python3-virtualenv` package which will allow us to create a virtual environment.

```bash
$ sudo dnf install python3-virtualenv
```

Now you can create a virtual environment called `project_venv` which will contain the Python 3.5 and a copy of the pip library.

```bash
$ virtualenv -p /usr/bin/python3.5 project_venv
```

If you want to work in the virtual environment, you have to activate it.

```bash
$ source project_venv/bin/activate
```

When the virtual environment is activated (you can see it's name in brackets at the beginning of your prompt), you can install modules with `pip3`.

```bash
(project_venv) $ pip3 install name_of_module
```

When you finish your work, just deactivate the virtual environment.

```bash
(project_venv) $ deactivate
```

### What next?

 * [PyPI - the Python Package Index](https://pypi.python.org/)
 * [The Hitchhiker's Guide to Python: Virtual Environments](http://docs.python-guide.org/en/latest/dev/virtualenvs/)

