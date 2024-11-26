# neovim-gnome-terminal-wrapper

![screenshot](screenshot.gif)

Wraps the neovim binary in a separate gnome-terminal session, making it
possible to use it as a regular application (it is tracked correctly by the DE,
it can be associated to filetypes, etc.)

## Requisites

* neovim
* gnome-terminal >= 3.16 (uses gnome-terminal-server)
* python-dbus

## Setup

On Ubuntu 20.04

Copy or link nvim-wrapper somewhere into the desktop environment's path and install the .desktop file.

~~~
cp nvim-wrapper ~/bin/nvim-wrapper
cp neovim.desktop ~/.local/share/applications/neovim.desktop
cp neovim.png ~/.local/share/icons/neovim.png
~~~

### Caveats when using running from virtual environments

Some users have experienced trouble running nvim-wrapper when inside a virtual environment created by e.g. virtualenv, conda or similar.
One workaround is to point the nvim-wrapper script directly to the right (system) python3 executable, i.e. change: 

~~~
#! /usr/bin/env python3
~~~

into:

~~~
#! /usr/bin/python3
~~~

After this, make sure the neovim python package is installed from the correct package manager, e.g. in Ubuntu:

~~~
/usr/bin/pip3 install --user neovim
~~~
