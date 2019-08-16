# dmux
*Development environment using tmux, vifm, and neovim*

## Prerequisites
- tmux
- vifm
- neovim
- neovim-remote

## Installation
#### Step one
Place the dmux file in your PATH and make sure it is excutable `chmod +x dmux`
#### Step two
Add an alias to replace neovim of vim in your `~/.bashrc` file: 
```
alias vim='dmux vim'
```
*This way vim will continue to work the same when not in dmux*
## Usage
#### Initialize dmux environment
`dmux init`

#### New dmux window inside tmux
`dmux new`
