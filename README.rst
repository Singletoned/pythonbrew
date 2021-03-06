Overview
========

pythonbrew is a program to automate the building and installation of Python in the users HOME.

pythonbrew is based on `perlbrew <http://github.com/gugod/App-perlbrew>`_.

Installation
============

The recommended way to download and install pythonbrew is to run these statements in your shell.::

  curl -kL http://github.com/utahta/pythonbrew/raw/master/pythonbrew-install | bash

After that, pythonbrew installs itself to ~/.pythonbrew, and you should follow the instruction on screen to setup your .bashrc or .cshrc to put it in your PATH.

If you need to install pythonbrew into somewhere else, you can do that by setting a PYTHONBREW_ROOT environment variable.::

  export PYTHONBREW_ROOT=/path/to/pythonbrew
  ./pythonbrew-install

Usage
=====

pythonbrew command [options]
    
Install some Pythons::

  pythonbrew install 2.6.6
  pythonbrew install --force 2.5.5
  pythonbrew install --configure="CC=gcc_4.1" 2.6.6
  pythonbrew install --no-setuptools 2.6.6
  pythonbrew install http://www.python.org/ftp/python/2.7/Python-2.7.tgz
  pythonbrew install file:///path/to/Python-2.7.tgz
  pythonbrew install /path/to/Python-2.7.tgz
  
Switch python in the PATH::

  pythonbrew switch 2.6.6
  pythonbrew switch 2.5.5

Using python in the PATH (current shell only)::

  pythonbrew use 2.6.6

Runs a named python file against specified and/or all pythons::

  pythonbrew py test.py
  pythonbrew py -v test.py # Show version
  pythonbrew py -p 2.6.6 -p 3.1.2 test.py # Using specified python versions

List the installed versions of Python::

  pythonbrew list

List the available install versions of Python::

  pythonbrew list -k

Uninstall some Pythons::

  pythonbrew uninstall 2.6.6

Remove stale source folders and archives::

  pythonbrew clean

Upgrades pythonbrew to the latest version::

  pythonbrew update

Disable pythonbrew::

  pythonbrew off

Show version::

  pythonbrew version

COMMANDS
========

install <version>
  Build and install the given version of python.
  
  Setuptools and pip is automatically installed.
  
  options: --force, --no-setuptools and --configure.

installed
  List the installed versions of python.

switch <version>
  Switch to the given version of python.

use <version>
  Using the given version of python.
  (current shell only)

py <python file>
  Runs a named python file against specified and/or all pythons.

list
  List the installed all pythons.
  
list -k <version>
  List the available install pythons.
  
uninstall <version>
  Uninstall the given version of python.

clean
  Remove stale source folders and archives.

update
  Upgrades pythonbrew to the latest version.

off
  Disable pythonbrew.

version
  Show version.

Options
=======

\-f | --force
  Force installation of a python. (skip `make test`)

\-C | --configure
  Custom configure options.

\-n | --no-setuptools
  Skip installation of setuptools.

COPYRIGHT
=========

Copyright (c) 2010, utahta "<labs.ninxit@gmail.com>".

LICENCE
=======

The MIT License
