# git-multihook

Configure multiple global and local directories for git hooks.


## Setup
Clone this repository
```sh
$ git clone https://github.com/coloursofnoise/git-multihook.git
```

Tell git to always run hooks in the cloned repository
```sh
$ git config --global core.hooksPath "$(PWD)/git-multihook"
```


## Configuration
The `multihook.hooksPath` git configuration variable can be set to a colon-separated list of paths, each of which will be checked for hook scripts when any git hook is run.

Default: `./.git/hooks`

```sh
$ git config --global multihook.hooksPath "${HOME}/.config/git/hooks:./.git/hooks"
```


## How it works
Setting `core.hooksPath` globally causes git to look for hooks within the
specified directory. This repository contains hooks that will look for and
run their corresponding hooks in every directory in the `multihook.hooksPath` configuration variable.
