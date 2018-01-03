# Adding Branch name to Windows Ubuntu Bash

Instructions for adding the current branch name at the end of your bash terminal. This is intended for the WIndows Ubuntu Subsystem bash.

## Open .bashrc

Open your Ubuntu terminal and type the following command:

```bash
nano ~/.bashrc
```

## Add our git branch code at bottom of file

Move to the bottom of the file and paste the following code:

```bash
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\033[01;36m$(parse_git_branch)\[\033[00m\]\$ '
```

_You can change the colors as needed._

Save your .bashrc file
