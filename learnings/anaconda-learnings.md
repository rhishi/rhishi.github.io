# Anaconda Learnings

`conda update --all` is useful even immediately after fresh install of Anaconda
(well, technically, Miniconda).  It updates several packages even if the install
script just installed them.

If you want to put `source activate python2` in your `~/.bash_profile`, you
might also want to unset `changeps1` flag in Anaconda config.

```
conda config --set changeps1 False
```
