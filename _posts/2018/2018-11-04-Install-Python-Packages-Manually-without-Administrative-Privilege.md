---
layout: post
title: Install Python Packages Manually
category: python
tags: [python]
---

# Install Python Packages Manually without Admin Privilege

## Normal procedure
    1. Download the package
    2. unzip it if it is zipped
    3. cd into the directory containing setup.py
    4. If there are any installation instructions contained in documentation contianed herein, read and follow the instructions OTHERWISE
    5. type in python setup.py install --user
    
## Abnormal issues

### Error could not download dependencies from internet

#### Phenomenon

    ``` 
    Download error on https://pypi.python.org/simple/pytest-runner/: unknown url type: https -- Some packages may not be found!
    Couldn't find index page for 'pytest-runner' (maybe misspelled?)
    Download error on https://pypi.python.org/simple/: unknown url type: https -- Some packages may not be found!
    No local packages or working download links found for pytest-runner
    Traceback (most recent call last):
    ```

#### Countermeasure

    1. Download the package specified by the error, in this case: https://pypi.python.org/simple/pytest-runner/
    2. unzip it if it is zipped to the .eggs folder in current installing package (e.g. "C:\Python27\Lib\pylint\.eggs")
    3. cd into the directory containing setup.py of current installing package (e.g. "C:\Python27\Lib\pylint")
    4. If there are any installation instructions contained in documentation contianed herein, read and follow the instructions OTHERWISE
    5. type in python setup.py install --user

## Tested on following packages
    1. selenium (automating stuffs on web browsers)
    2. pylint (syntax error suggestion)
    3. colorama (allows to print colored text to output console)

## Ref