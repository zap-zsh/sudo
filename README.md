# sudo
### This is an intresting plugin from [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/sudo),<BR>⚠️ please note that all credits are of oh-my-zsh team
---

##### This seeams doesn't work in combination with [zap-zsh/vim](https://github.com/zap-zsh/vim), althogh it works with standard ZSH VI mode (`bindkey -v`)

Easily prefix your current or previous commands with `sudo` by pressing <kbd>esc</kbd> twice.

## Usage

To use it, add `"zap-zsh/sudo"` to the plugins in your zshrc file:

```zsh
plug "zap-zsh/sudo"
```
  
### Current typed commands

Say you have typed a long command and forgot to add `sudo` in front:

```console
$ apt-get install build-essential
```

By pressing the <kbd>esc</kbd> key twice, you will have the same command with `sudo` prefixed without typing:

```console
$ sudo apt-get install build-essential
```

The same happens for editing files with your default editor (defined in `$SUDO_EDITOR`, `$VISUAL` or `$EDITOR`, in that order):

If the editor defined were `vim`:

```console
$ vim /etc/hosts
```

By pressing the <kbd>esc</kbd> key twice, you will have the same command with `sudo -e` instead of the editor, that would open that editor with root privileges:

```console
$ sudo -e /etc/hosts
```

### Previous executed commands

Say you want to delete a system file and denied:

```console
$ rm some-system-file.txt
-su: some-system-file.txt: Permission denied
$
```

By pressing the <kbd>esc</kbd> key twice, you will have the same command with `sudo` prefixed without typing:

```console
$ rm some-system-file.txt
-su: some-system-file.txt: Permission denied
$ sudo rm some-system-file.txt
Password:
$
```

The same happens for file editing, as told before.

## Key binding

By default, the `sudo` plugin uses <kbd>Esc</kbd><kbd>Esc</kbd> as the trigger.
If you want to change it, you can use the `bindkey` command to bind it to a different key:

```sh
bindkey -M emacs '<seq>' sudo-command-line
bindkey -M vicmd '<seq>' sudo-command-line
bindkey -M viins '<seq>' sudo-command-line
```

where `<seq>` is the sequence you want to use. You can find the keyboard sequence
by running `cat` and pressing the keyboard combination you want to use.
