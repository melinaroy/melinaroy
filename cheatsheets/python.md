# Python Cheatsheet

Useful Python commands and practices.

## 🐍 General

```bash
# check Python version
python --version

# run a Python script
python script.py

# start interactive Python shell
python
```

## 🧪 Virtual Environment

```bash
# create a virtual environment
python -m venv venv

# activate virtual environment (Windows)
venv\\Scripts\\activate

# activate virtual environment (Unix/Mac)
source venv/bin/activate

# deactivate virtual environment
deactivate
```

## 📦 Packages

```bash
# install a package
pip install <package_name>

# uninstall a package
pip uninstall <package_name>

# upgrade a package
pip install --upgrade <package_name>

# check installed packages
pip list

# show package location and details
pip show <package_name>

# install packages from requirements.txt
pip install -r requirements.txt

# export installed packages to requirements.txt
pip freeze > requirements.txt
```
