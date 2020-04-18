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
alias vifm='dmux vifm'

```
*This way vim and vifm will continue to work the same when not in dmux*

#### Step three
Add the following lines to the top your `.tmux.conf` file
```
source ~/.dmux.conf
```
*This way you will be able to override defaults*

#### Step four
Change the `default_projects_dir="$HOME/Cloud/Development/projects"` variable in the dmux file to match your project folders location
*dmux will automatically add a bin and web directory in the `default_projects_dir` location to store your projects in when you create your projects using `dmux new [project_name]`

## Usage
#### Initialize dmux environment
`dmux init # (or simply dmux)`<br/>
`dmux [file] # opens dmux and opens file in vim and vifm`<br/>
`dmux [directory] # opens dmux and opens directory in vifm`<br/>

#### New dmux window (inside of tmux)
`dmux window`

#### New dmux project
`dmux new [project_name]`

#### New dmux project by cloning a git repo
`dmux clone [htts://repo.git] [project_name is optional]`

#### Open a dmux project with interactivly
`dmux open`
