# Anaconda Learnings

## Why Anaconda

Anaconda Python is a distribution of Python that comes with its own package
manager, `conda`, that lets you install Python packages.  `conda` also lets you
create different Python environments.

So why not standard Python, pip, and virtualenv?  The one and only reason that
I found originally, sometime in early 2010s, is that pip is great for installing
pure-Python packages, but falls short with packages that have some native,
binary component, e.g. NumPy with an optimized linear algebra library.  Anaconda
installs the right stuff no matter it's pure-Python or Python+Native.

## Install

I choose Miniconda, a smaller distribution with just Python and a few other
necessary packages, over the full Anaconda distribution.

Document on downloading conda
https://conda.io/docs/user-guide/install/download.html<br>
Download Anaconda
https://www.anaconda.com/download/<br>
Download Miniconda
https://conda.io/miniconda.html<br>

The installers come in Python 2 and Python 3 variants.
In August 2018, the versions were Python 2.7 and Python 3.6.
I choose Python 2 as the base, and then easily create a Python 3 environment.

macOS Miniconda Python 2 installer:
https://repo.continuum.io/miniconda/Miniconda2-latest-MacOSX-x86_64.sh

`conda update --all` is useful even immediately after fresh install of Anaconda
(well, technically, Miniconda).  It updates several packages even if the install
script just installed them.

## Environments

Create a new Python 2 environment (just to be symmetric with Python 3
environment that I create later):

```
conda create -n python2 python=2.7
```

If you want to put `source activate python2` in your `~/.bash_profile`, you
might want to unset `changeps1` flag in Anaconda config.

```
conda config --set changeps1 False
```

Create new Python 3 environment:

```
conda create -n python3 python=3.6
```
