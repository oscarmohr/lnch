# 🚀 lnch -- fuzzy launcher, directory switcher and file opener

![demo](demo.gif)

`lnch` uses `fzf` to fuzzy find applications to run, `cd` into a fuzzy found directory, or opening a fuzzy found file in a default application with `rifle`.

## Usage
In a Terminal, run `lnch`:
```
$ lnch
```
to open a file.

To run a program:

```
$ lnch r
```

Use your window manager, desktop environment or `sxhkd` to map a keybinding to `$ $TERMINAL lnch`


Use `zsh` builtins to map a keybinding like `ctrl`+`f` to `lnch` and `ctrl`+`r` to `lnch r`:
```zsh
# zsh configuration file: $XDG_CONFIG_HOME/zsh/.zshrc
bindkey -s '^f' 'lnch\n'    # ctrl+f
bindkey -s '^r' 'lnch r\n'  # ctrl+r 
```


Additionally you can also just use:
```
$ detach program
```
to run a program named `program` directly from the terminal, without it rendering your calling terminal useless.


## Dependencies

Currently the dependencies are:
- `go`
- `fzf`
- `gnu-coreutils`
- `zsh` (`bash` and `sh` support coming soon!)
- `ranger` (for `rifle` in `$PATH`)

## Installation
On Arch Linux:
```zsh
$ sudo pacman -S go fzf zsh ranger
$ git clone "https://www.github.com/oscarmohr/lnch"
$ cd lnch
$ go build detach.go
$ chmod +x detach lnch
$ cp detach lnch $USER_BIN   # USER_BIN=$HOME/.local/bin is a dir for user binaries in PATH 
```

## Configuration

The main configuration file is `ranger.conf` usually located in `$XDG_CONFIG_HOME/rifle.conf` where `$XDG_CONFIG_HOME=$HOME/.config/` usually.  
There, you can choose which applications open which `MIME`-types. For more info read `man rifle`.

## Contribution
Feel free to contribute and send suggestions to improve the program.
A generally pleasing UI and a centralized PKGBUILD are on the roadmap.
