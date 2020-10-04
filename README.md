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
export DMUX_LAYOUTS='3840x1600:32f3,191x73,0,0{35x73,0,0,0,155x73,36,0[155x54,36,0,1,155x18,36,55,2]}|2560x1600:ea33,130x35,0,0{20x35,0,0,0,109x35,21,0[109x26,21,0,1,109x8,21,27,2]}'

```
##### DMUX_LAYOUTS format
The format of this variable should be `DMUX_LAYOUTS='resolution1:layout2|resolution1:layout2'` where resolution1 is the screen resolution (e.g. 3840x1600) and layout1 is tmux layout. To get the current resolution of the display on macos you can run the following command.

```system_profiler SPDisplaysDataType | grep Resolution | awk -F' ' '{print $2$3$4 }'```

To get the current layout of tmux, while tmux is running run the following command `tmux list-windows`. The output will look something like the following for each tmux window you have open.

```1: bash* (3 panes) [173x66] [layout a49c,173x66,0,0{26x66,0,0,0,146x66,27,0[146x50,27,0,1,146x15,27,51,2]}] @0 (active)```

Dmux only needs the layout from the above output which is everything after the keyword layout in the second set of brakets. 

You can have multiple layouts to account for different screen sizes. To do this simply add them to the DMUX_LAYOUTS varaible delimiting them a single pipe character.


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
