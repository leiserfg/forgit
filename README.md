# forgit

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://wfxr.mit-license.org/2017)

`forgit` is a utility tool for git taking advantage of fuzzy finder fzf.

## Installation

*Make sure you have [`fzf`](https://github.com/junegunn/fzf) installed.*

### Try Online

Run following command in your shell to try `forgit` without installing(for both `bash` and `zsh`):
``` bash
source <(curl -Ss https://raw.githubusercontent.com/wfxr/forgit/master/forgit.plugin.zsh)
```

### [Zplug](https://github.com/zplug/zplug)
``` zsh
zplug 'wfxr/forgit'
```

### [Zgen](https://github.com/tarjoilija/zgen)
``` zsh
zgen load wfxr/forgit
```

### [Antigen](https//github.com/zsh-users/antigen)
``` zsh
antigen bundle wfxr/forgit
```

### Manually

Download and source `forgit.plugin.zsh` or `forgit.plugin.sh` in your shell config.

## Commands

### ga

Interactive `git add` selector

![screenshot](https://raw.githubusercontent.com/wfxr/i/master/forgit-ga.png)

### glo

Interactive `git log` viewer

![screenshot](https://raw.githubusercontent.com/wfxr/i/master/forgit-glo.png)

### gi

Interactive `.gitignore` generator

![screenshot](https://raw.githubusercontent.com/wfxr/i/master/forgit-gi.png)

### gd

Interactive `git diff` viewer

### gcf

Interactive `git checkout <file>` selector

### gss

Interactive `git stash` viewer

### gclean

Interactive `git clean` selector


## Default keybinds

| Keybind                                       | Action                  |
| :-------------------------------------------: | ----------------------- |
| <kbd>Enter</kbd>                              | Confirm                 |
| <kbd>Tab</kbd>                                | Toggle mark             |
| <kbd>?</kbd>                                  | Toggle preview window   |
| <kbd>Ctrl</kbd> - <kbd>S</kbd>                | Toggle sort             |
| <kbd>Ctrl</kbd> - <kbd>R</kbd>                | Toggle selection        |
| <kbd>Alt</kbd> - <kbd>W</kbd>                 | Toggle preview wrap     |
| <kbd>Ctrl</kbd> - <kbd>K</kbd> / <kbd>P</kbd> | Selection up            |
| <kbd>Ctrl</kbd> - <kbd>J</kbd> / <kbd>N</kbd> | Selection down          |
| <kbd>Alt</kbd> - <kbd>K</kbd> / <kbd>P</kbd>  | Preview up              |
| <kbd>Alt</kbd> - <kbd>J</kbd> / <kbd>N</kbd>  | Preview down            |

## Custom options

You can change the default aliases by defining these variables below.
(To disable all aliases, Set the `FORGIT_NO_ALIASES` flag.)

``` bash
# Define them before sourcing the plugin if you don't use any plugin manager.
forgit_log=glo
forgit_diff=gd
forgit_add=ga
forgit_ignore=gi
forgit_restore=gcf
forgit_clean=gclean
forgit_stash_show=gss
```

You can add custom fzf options for `forgit`, including keybinds, layout, etc.
(No need to repeat the options already defined in `FZF_DEFAULT_OPTS`)

``` bash
FORGIT_FZF_DEFAULT_OPTS="
--exact
--border
--cycle
--reverse
--height '80%'
"
```
## Optional

- [`diff-so-fancy`](https://github.com/so-fancy/diff-so-fancy): Improve the `git diff` output.

- [`bat`](https://github.com/sharkdp/bat.git): Syntex highlight for `gitignore`.

- [`emoji-cli`](https://github.com/wfxr/emoji-cli): Emoji support for `git log`.

## Tips

- Hit `q` to quit from full screen preview any time.
- Commands like `glo`, `gd`, `gcf` and `gclean` accept path arguments to restrain the items listed in fzf(eg, `glo main.go test.go`, `gclean output/`).
- Call `gi` with arguments to get the wanted `.gitignore` contents directly(eg, `gi cmake c++`).

## License

[MIT](https://wfxr.mit-license.org/2017) (c) Wenxuan Zhang
