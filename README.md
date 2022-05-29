
.Oh My Zsh
==========

By @ohmyzsh

[https://github.com/santiandres33/ohmyzsh](https://github.com/santiandres33/ohmyzsh#basic-installation)

Basic Installation
Oh My Zsh is installed by running one of the following commands in your terminal. You can install this via the command-line with either curl, wget or another similar tool.

Installation
------------

## Getting Started

### Prerequisites

- A Unix-like operating system: macOS, Linux, BSD. On Windows: WSL2 is preferred, but cygwin or msys also mostly work.
- [Zsh](https://www.zsh.org) should be installed (v4.3.9 or more recent is fine but we prefer 5.0.8 and newer). If not pre-installed (run `zsh --version` to confirm), check the following wiki instructions here: [Installing ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)
- `curl` or `wget` should be installed
- `git` should be installed (recommended v2.4.11 or higher)

### Basic Installation

Oh My Zsh is installed by running one of the following commands in your terminal. You can install this via the command-line with either `curl`, `wget` or another similar tool.

| Method    | Command                                                                                           |
| :-------- | :------------------------------------------------------------------------------------------------ |
| **curl**  | `REPO=santiandres33/ohmyzsh sh -c "$(curl -fsSL https://raw.githubusercontent.com/santiandres33/ohmyzsh/master/tools/install.sh)"` |
| **wget**  | `REPO=santiandres33/ohmyzsh sh -c "$(wget -O- https://raw.githubusercontent.com/santiandres33/ohmyzsh/master/tools/install.sh)"`   |
| **fetch** | `REPO=santiandres33/ohmyzsh sh -c "$(fetch -o - https://raw.githubusercontent.com/santiandres33/ohmyzsh/master/tools/install.sh)"` |

_Note that any previous `.zshrc` will be renamed to `.zshrc.pre-oh-my-zsh`. After installation, you can move the configuration you want to preserve into the new `.zshrc`._

.Oh My Tmux
=====

By @gpakosz

Self-contained, pretty and versatile `.tmux.conf` configuration file.

![Screenshot](https://cloud.githubusercontent.com/assets/553208/19740585/85596a5a-9bbf-11e6-8aa1-7c8d9829c008.gif)

Installation
------------

To install, run the following from your terminal: (you may want to backup your
existing `~/.tmux.conf` first)

```
sudo apt update && sudo apt install cmake tmux git xclip -y && sudo git clone https://github.com/santiandres33/.tmux.git /etc/oh-my-tmux && ln -s -f /etc/oh-my-tmux/.tmux.conf ~/.tmux.conf && cp /etc/oh-my-tmux/.tmux.conf.local ~/.tmux.conf.local
```

Then proceed to [customize] your `~/.tmux.conf.local` copy.

[customize]: #configuration

If you're a Vim user, setting the `$EDITOR` environment variable to `vim` will
enable and further customize the vi-style key bindings (see tmux manual).

If you're new to tmux, I recommend you read [tmux 2: Productive Mouse-Free
Development][bhtmux2] by [@bphogan].

[bhtmux2]: https://pragprog.com/book/bhtmux2/tmux-2
[@bphogan]: https://twitter.com/bphogan


Features
--------

 - `C-f` acts as secondary prefix, while keeping default `C-b` prefix
 - visual theme inspired by [Powerline][]
 - [maximize any pane to a new window with `<prefix> +`][maximize-pane]
 - SSH/Mosh aware username and hostname status line information
 - mouse mode toggle with `<prefix> m`
 - automatic usage of [`reattach-to-user-namespace`][reattach-to-user-namespace]
   if available
 - laptop battery status line information
 - uptime status line information
 - optional highlight of focused pane
 - configurable new windows and panes behavior (optionally retain current path)
 - SSH/Mosh aware split pane (reconnects to remote server)
 - copy to OS clipboard (needs [`reattach-to-user-namespace`][reattach-to-user-namespace]
   on macOS, `xsel` or `xclip` on Linux)
 - support for 4-digit hexadecimal Unicode characters
 - [Facebook PathPicker][] integration if available
 - [Urlview][] integration if available

[Powerline]: https://github.com/Lokaltog/powerline
[maximize-pane]: http://pempek.net/articles/2013/04/14/maximizing-tmux-pane-new-window/
[reattach-to-user-namespace]: https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard
[Facebook PathPicker]: https://facebook.github.io/PathPicker/
[Urlview]: https://packages.debian.org/stable/misc/urlview



![Maximize pane](https://cloud.githubusercontent.com/assets/553208/9890858/ee3c0ca6-5c02-11e5-890e-05d825a46c92.gif)



![Mouse mode](https://cloud.githubusercontent.com/assets/553208/9890797/8dffe542-5c02-11e5-9c06-a25b452e6fcc.gif)

Cheatshhet Oh-My-Tmux
--------

## Cheat Sheet

### SESSION
- tmux new -s myses 	##Start a new session with the name *myses*
- tmux kill-ses -t mysession
- tmux ls
- tmux a 	## Attach to last session
- tmux a -t mysession
- Prefix  ( 	##Move to previous session
- Prefix  ) 	## Move to next session
- Prefic C - c ## Creates new session


### WINDOW
- Prefix c	## Create window
- Prefix  ,	## Rename current window
- Prefix  &	## Close current window
- Prefix  p	## Previous window
- Prefix  n	## Next window
- Prefix  space 	## Toggle windows
- Prefix  0 ... 9

### PANES
- Prefix  x	## Close pane 	
- Prefix  ;	## Toggle last active pane
- Prefix  - or _
- Prefix  | or \

### COPY MODE 
- Prefix  [	 ## Enter copy mode

- q	 ## Quit mode
- g	 ## Go to top line
- G	 ## Go to bottom line
- /	 ## Search forward
- ?	 ## Search backward
- n	 ## Next keyword occurance
- N	 ## Previous keyword occurance
- v   ##begins selection / visual mode
- C-v ## toggles between blockwise visual mode and visual mode
- H   ##jumps to the start of line
- L   ##jumps to the end of line
- y   ##copies the selection to the top paste-buffer
- Escape ##cancels the current operation

### Others

 - `<prefix> e` opens `~/.tmux.conf.local` with the editor defined by the
   `$EDITOR` environment variable (defaults to `vim` when empty)
 - `<prefix> r` reloads the configuration
 - `C-l` clears both the screen and the tmux history
 - `<prefix> C-h` and `<prefix> C-l` let you navigate windows (default
 - `<prefix> Tab` brings you to the last active window
 - `<prefix> <` and `<prefix> >` let you swap panes
 - `<prefix> +` maximizes the current pane to a new window
 - `<prefix> m` toggles mouse mode on or off
 - `<prefix> b` lists the paste-buffers
 - `<prefix> p` pastes from the top paste-buffer
 - `<prefix> P` lets you choose the paste-buffer to paste from




Configuration
-------------

While this configuration tries to bring sane default settings, you may want to
customize it further to your needs. Instead of altering the `~/.tmux.conf` file
and diverging from upstream, the proper way is to edit the `~/.tmux.conf.local`
file.

Please refer to the sample `.tmux.conf.local` file to know more about variables
you can adjust to alter different behaviors. Pressing `<prefix> e` will open
`~/.tmux.conf.local` with the editor defined by the `$EDITOR` environment
variable (defaults to `vim` when empty).

### Enabling the Powerline look MacOS

To make use of these symbols, there are several options:

- use a font that already bundles those: this is e.g. the case of the
  [2.030R-ro/1.050R-it version][source code pro] of the Source Code Pro font
- use a [pre-patched font][powerline patched fonts]
- use your preferred font along with the [Powerline font][powerline font] (that
  only contains the Powerline symbols): [this highly depends on your operating
  system and your terminal emulator][terminal support], for instance here's a
  screenshot of iTerm2 configured to use `PowerlineSymbols.otf`
  ![iTerm2 + Powerline font](https://user-images.githubusercontent.com/553208/62243890-8232f500-b3de-11e9-9b8c-51a5d38bdaa8.png)

[source code pro]: https://github.com/adobe-fonts/source-code-pro/releases/tag/2.030R-ro/1.050R-it
[powerline patched fonts]: https://github.com/powerline/fonts
[powerline font]: https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf
[terminal support]: http://powerline.readthedocs.io/en/master/usage.html#usage-terminal-emulators
[Powerline manual]: http://powerline.readthedocs.org/en/latest/installation.html#fonts-installation

Please see the [Powerline manual] for further details.

Then edit your `~/.tmux.conf.local` copy (with `<prefix> e`) and adjust the
following variables:

```
tmux_conf_theme_left_separator_main='\uE0B0'
tmux_conf_theme_left_separator_sub='\uE0B1'
tmux_conf_theme_right_separator_main='\uE0B2'
tmux_conf_theme_right_separator_sub='\uE0B3'
```
## Additional Configurations
### Manual
-Transparency

-Shortcut to switch tabs

-Show bold text in bright colors

### Custom ~/.zshrc 
Copied during Oh-My-Zsh installation 
https://github.com/santiandres33/ohmyzsh/blob/master/templates/zshrc.zsh-template

## Oh-My-Zsh Favorite themes
#### Tjkirch 
``` https://github.com/santiandres33/ohmyzsh/blob/master/themes/tjkirch.zsh-theme ```
#### Xiong-chiamiov-plus
``` https://github.com/santiandres33/ohmyzsh/blob/master/themes/xiong-chiamiov-plus.zsh-theme ```
#### Kali
```https://github.com/santiandres33/ohmyzsh/blob/master/custom/themes/kali.zsh-theme ```
## Oh-My-Zsh favorite plugins
 plugins=(nmap git docker zsh-completions zsh-autosuggestions)
 
#### Install zsh-completions Debian
https://github.com/zsh-users/zsh-completions
```
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions
```
```
 fpath+=${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions/src
```
#### Install zsh-autosuggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
```
plugins=( 
    # other plugins...
    zsh-autosuggestions
)
```
