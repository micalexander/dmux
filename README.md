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
Set environment variables. DMUX_PROJECTS is required and should point to where you would like dmux to store your projects. Is optional and is used to set your default layout. These can be set in your ~/.bashrc
```
export DMUX_PROJECTS=$HOME/Cloud/Development/projects
export DMUX_LAYOUT='32f3,191x73,0,0{35x73,0,0,0,155x73,36,0[155x54,36,0,1,155x18,36,55,2]}'
```

## Usage

#### Initialize dmux environment
`dmux # opens a dmux enabled tmux session in the current directory`<br/>
`dmux [file] # opens dmux and opens file in vim and vifm`<br/>
`dmux [directory] # opens dmux and opens directory in vifm`<br/>

#### New dmux project
`dmux new [project_name]`

#### New dmux project by cloning a git repo
`dmux clone [htts://repo.git] [project_name is optional]`

#### Open a dmux project with interactivly
`dmux open`

#### New dmux window (inside of tmux)
`dmux window`
