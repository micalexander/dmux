# dmux
*Development environment using tmux, vifm, and neovim*

## Prerequisites
- tmux
- vifm
- neovim
- neovim-remote
- fzf
- fd
```
brew install tmux vifm neovim fzf fd
pip3 neovim-remote
```

## Installation
#### Step one
Place the dmux file in your PATH and make sure it is excutable `chmod +x dmux`
#### Step two
Add an alias to replace neovim of vim in your `~/.bashrc` file: 
```
alias vim='dmux vim'
```
*This way vim will continue to work the same when not in dmux*
# Step three
Change the `default_projects_dir="$HOME/Cloud/Development/projects"` variable in the dmux file to match your project folders location
*dmux will automatically add a bin and web directory in the `default_projects_dir` location to store your projects in when you create your projects using `dmux new [project_name]`

## Usage
#### Initialize dmux environment
`dmux init # or simply dmux`

#### New dmux window (inside of tmux)
`dmux new`

#### New dmux project (outside of tmux)
`dmux new [project_name]`

#### Open a dmux project with FZF
`dmux open`
