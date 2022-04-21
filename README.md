# py3-CHIRP
A fork of CHIRP for testing with Python 3.

## What's Different?
The official CHIRP project's main branch does not support Python 3 and depends on pygtk which hasn't seen a stable release since April 2011.

py3-CHIRP is a fork of the py3 branch of the official [CHIRP project](https://chirp.danplanet.com/projects/chirp/wiki/Home). 

py3-CHIRP will use the wxPython GUI toolkit. Code using the Gtk GUI will be migrated.

## Dependencies

py3-CHIRP has been tested in Python3.9 on various platforms. Known dependencies that don't come out of the box with Python are as follows:
- pyserial
- wxPython
- future
- six
- pypiwin32 (for Windows)
- pyGObject (For the time being)
- libpython-dev (For Ubuntu users)

## Testing

For a list of supported radios (tested and untested) see [RADIOS.md](https://github.com/mpoletiek/py3-CHIRP/blob/main/RADIOS.md)

### Creating a Development Environment

#### Windows 

The project requires pyGObject and the path of least resistance is
[msys2](https://www.msys2.org/). This will also provide a more
unix-like python environment that may make developing cross-platform
simpler.

Open a `msys2` terminal and install the dependencies:

```shell
pacman -Syu
pacman -S mingw-w64-x86_64-python-pywin32 mingw-w64-x86_64-gtk3 mingw-w64-x86_64-python3 mingw-w64-x86_64-python3-gobject mingw-w64-python-py2exe mingw-w64-x86_64-wxPython
```

Create a virtualenv for development (in MSYS)

```shell
python -m venv --system-site-packages .venv
./.env/bin/pip install -r requirements.txt -r test-requirements.txt -e .
```

Now this environment can accessed from your prompt or IDE of choice, such as
VSCode or PyCharm.

### Running py3-CHIRP
`chirpwx.py`

**DO NOT USE** `chirpw`

## REFERENCE

### Wiki
 - [GitHub](https://github.com/mpoletiek/py3-CHIRP/wiki)

### Repo Source (Forked From)

 - Mercurial Repository: http://d-rats.com/hg/chirp.hg
 - Revision: py3
 - Number:	3351:68534f20c141

### Bugs and Patches Submitted to Official Project

 - https://chirp.danplanet.com/issues/8475 - Fixed old Python2 Syntax
 - https://chirp.danplanet.com/issues/8545 - Syntax Errors in Driver Files
 - https://chirp.danplanet.com/issues/8549 - Updated `string.uppercase` to `string.ascii_uppercase`

### Related Bugs in Gentoo

 - https://bugs.gentoo.org/708304 - Removed CHIRP from Portage


## The Story

When I first started using Gentoo again CHIRP was still a part of the main Gentoo Portage Repository.

Eventually Gentoo began migrating away from Python2 and due to a lack of movement in the official project it was removed from the official Gentoo repository. 

I still needed to configure my radios and maintain an up to date Gentoo desktop so I cloned the py3 branch from the official CHIRP project and fixed a few syntax errors leftover from Python2 and everything worked great.

I was able to download an image from my BF-F8HP, fully reconfigure it and upload the new image back to my radio.

After this initial test I started bugging the developers maillinglist of the main project for more information. A few individuals reached out offering help and asking me to share what I had. So, this repo was born. 

