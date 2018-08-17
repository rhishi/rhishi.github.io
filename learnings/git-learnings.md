# Git Learnings

## Git Bash Completion

The Pro Git Book v2 [Git in Bash](https://git-scm.com/book/en/v2/Appendix-A%3A-Git-in-Other-Environments-Git-in-Bash)
says:

  1. Get `git-completion.bash`, e.g. from [github/git/git/contrib/completion/git-completion.bash](https://github.com/git/git/blob/master/contrib/completion/git-completion.bash).
  2. Put it somewhere on your machine, e.g. the home directory.
  3. Add `. <path>/git-completion.bash` to your `~/.bashrc`.<br>
     Or `source <path>/git-completion.bash` reads better.

The Pro Git Book v1 [Git Basics - Tips and Tricks](https://git-scm.com/book/en/v1/Git-Basics-Tips-and-Tricks) also offers:

  4. To enable completion automatically for all users, put `git-completion.bash` in `/etc/bash_completion.d/` directory.

Aug 2018: macOS: simply putting `git-completion.bash` in `/etc/bash_completion.d/` directory did not enable completion in new Terminal window.

Aug 2018: macOS: Using the latest `git-completion.bash` with macOS built-in `/usr/bin/git` gave errors,<br>
-- e.g. type "git sta", press TAB, and get "Unknown option: --list-cmds=...".

### The Homebrew Way

As recommended by [bobthecow/git-flow-completion](https://github.com/bobthecow/git-flow-completion/wiki/Install-Bash-git-completion), the best is to:

1. Install `git` and `bash-completion` packages via Homebrew
   ```
   brew install git bash-completion
   ```
2. Add the following line to `~/.bash_profile`
   ```
   [ -f /usr/local/etc/bash_completion ] && . /usr/local/etc/bash_completion
   ```

## Git Aliases

The Pro Git Book v2 gives a few good aliases: `co`, `br`, `ci`, `st`.<br>
https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases

```
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

The Pro Git Book v2 also gives an advanced alias: `unstage`.

```
git config --global alias.unstage 'reset HEAD --'
```

Remember, `git status` tells you exactly the above for unstaging your changes.<br>
Also, [Git Reset Demystified](https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified)
tells us:
  - The default mode of `reset` is `--mixed`, which
    1. moves the branch that HEAD points to, and
    2. makes the index look like HEAD, and
    3. does not touch the working tree.
  - But when providing paths, the first step is skipped anyway.
  - but anyway we say HEAD, so the first step is a no-op even if it happens.
  - `--` is good practice that ensures the arguments are treated as paths, file
    names and not confused with Git options or tags or branch names etc.

Another good alias given in the Pro Git Book v2 is `last`.

```
git config --global alias.last 'log -1 HEAD'
```

This shows the latest commit on the current branch.
Also useful as `git last -p` to see the patch of the commit.

An alias that is kind of my own design is `count`.  It displays the number of
commits reachable back in history from given commit(s).

```
git config --global alias.count 'rev-list --count'
```

The last trick on aliases in the Pro Git Book v2 is to make alias to launch an
external command.  Use `!` before the command to indicate that it is not a Git
sub-command but an external command.  The book demonstrates this with alias
`visual` set to launch `gitk`.

It is equally useful for launching GitHub Desktop using its commandlet
`/usr/local/bin/github`.  What's nice is, if you already have GitHub Desktop
running, then executing `github` from a directory that is a Git repository
switches the already-open GitHub Desktop window to that repository.

```
git config --global alias.visual '!gitk'
git config --global alias.hub '!github'
```

Oh well, the commandlet `github` is already nicer than any Git alias.

One could choose from several Git GUI clients from this page:
https://git-scm.com/download/gui/mac
  * SourceTree
  * [GitUp](http://gitup.co) -- only on macOS; free; open-source; kind of nice

```
git config --global alias.up '!gitup'
```

The above adds an alternative in addition to the GitUp commandlet.
Again, the commandlet `gitup` itself is shorter than alias `git up`.

Like the GitHub Desktop commandlet, the GitUp commandlet also detects whether
the current working directory is a Git repository and opens its window in GitUp.
