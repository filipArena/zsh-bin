# zsh-bin

> Statically-linked, hermetic, relocatable Zsh.

## Installation

To install Zsh on x86_64 Linux box without root access, run the following commands:

```sh
mkdir -p ~/apps
cd ~/apps
curl -fsSLO https://github.com/romkatv/zsh-bin/releases/download/v1.0.0/zsh-5.8-linux-x86_64-static.tar.gz
tar -xzf zsh-5.8-linux-x86_64-static.tar.gz
zsh-5.8-linux-x86_64-static/share/zsh/5.8/scripts/relocate
rm -f zsh-5.8-linux-x86_64-static.tar.gz
```

*Note*: If there is no `curl` on your machine, try replacing `curl -fsSLO` with `wget`.

After that you can invoke `~/apps/zsh-5.8-linux-x86_64-static/bin/zsh` and it'll just work,
although you'll probably want to add `~/apps/zsh-5.8-linux-x86_64-static/bin` to `PATH` for
convenience.

If you move or rename `~/apps/zsh-5.8-linux-x86_64-static`, remember to call `.../relocate`
afterwards. This script configures Zsh so that it loads builtin functions from the new location.

## Compiling

```sh
git clone https://github.com/romkatv/zsh-bin.git
cd zsh-bin
./build-zsh-5.8-static
```

This creates `zsh-5.8-linux-x86_64-static.tar.gz` in the current directory. This archive contains
statically-linked, hermetic, relocatable Zsh 5.8. Installation of Zsh from the archive doesn't
require libc, terminfo, ncurses or root access. As long as the target machine has a compatible CPU
and Linux kernel, it'll work.

You can find built archives in [releases](https://github.com/romkatv/zsh-bin/releases).