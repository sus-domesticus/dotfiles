# Configuration files for various tools

## Prerequisites

I have tested most of these files only on Linux.

For cross-platform tools like [neovim](https://github.com/neovim/neovim) you can
manually copy and install their config files.

[GNU stow](https://www.gnu.org/software/stow/) should be used to install these files.
Check out the documentation of stow by running `info stow` and check out how to manage
your dotfiles with stow [here](https://brandon.invergo.net/news/2012-05-26-using-gnu-stow-to-manage-your-dotfiles.html).

Run `stow -V` and make sure your version is at least `2.4.0` since earlier GNU stow
versions have a bug with regards to the `--dotfiles` flag.

### Structure

Each tool has its own directory. For example [neovim](https://github.com/neovim/neovim)
has the `nvim` folder at the root of this repo but its actual configuration files
are located in `nvim/dot-config/nvim/`. This structure makes it easy to install
these files with stow.

## Usage

First read the [prerequisites section](#prerequisites) if you haven't already.

I'll use neovim as an example tool below but these steps apply to everything else.

- `cd $HOME` (you need to `cd` in the home directory or else manually set
stow's `--target` flag to the directory where the files should be installed)
- `git clone --recurse-submodules https://github.com/sus-domesticus/dotfiles`
(the `--recurse-submodules` flag is needed because some of the tools
(neovim included) have their own repos embedded as
[submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) in this repo)
- `cd dotfiles` (`cd` to the root of this freshly-cloned repo)
- read the follow-up instructions from the [neovim subsection](#neovim).
(for other tools see their respective subsections in the [tools section](#tools))

## Tools

This section describes general information like prerequisites, tips and tricks
etc. for each tool. You should first follow the steps from the
[usage section](#usage) (if you haven't already) and then come here for specific
tool setup instructions/knowledge.

Each tool has its own subsection below.

### neovim

- See the [README of the neovim repo](https://github.com/sus-domesticus/config.nvim/blob/main/README.md)
(the repo is located in `nvim/dot-config/nvim/`).
- `stow --dotfiles nvim`

#### Common pitfalls

- If the `nvim/dot-config/nvim/` directory is empty you probably forgot to update
or initialize the [git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
(something like `git submodule update --init --recursive` should solve this problem).

### tmux

The config files have been tested for `tmux 3.4`. (run `tmux -V` to check your version)

- `stow --dotfiles tmux`
