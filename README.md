# Vim configuration

## Installation

This configuration is based on [Fisa VIM](https://vim.fisadev.com/) but I added 
some more Plugings.

### Install required packages

First you need to install some `apt` package
```sh
sudo apt install git curl python3-pip exuberant-ctags ack-grep
```

And now, you need to install some `Python` libraries. I recomend install only 
for one user
```sh
pip3 install pynvim flake8 pylint isort
```

You need to do a little modification in you `.bashrc` file adding the following
lines at the bottom

```sh
export PATH=$PATH:~/.local/bin
export PYTHONPATH=$PYTHONPATH:~/.local/bin
```

so now you can use the `Python` packages.

### Configure VIM

Download the file `vimrc` in your `home` directory and change it the name by 
`.vimrc`. Then do the same with the directory `vim` but the name should `.vim`.

Open _vim_ in a terminal and wait until all the plugins are installed.

## Details

### Python and coding

* **Smart autocompletion as you type**
    
* **Fuzzy file, code and command finders**
    - `,e` : file finder, with recursive (subdirectories) and fuzzy file name 
    matching. You can also open the files in a new tab with `Ctrl-t`.
    - `,g` : symbol finder (classes, methods, variables, functions, ...) in the current 
    file. `,G` does the same but on all opened files, `,wg` and `,wG` are variants that 
    search the current word under the cursor.
    - `,c` : command finder (internal vim commands, or custom commands).
    - `,f` : "any text" finder in the current file. ,F does the same but on all opened 
    files, ,wf and ,wF are variants that search the current word under the cursor.

* Some other neat Python magic spells:
    - `,d` : go to definition of the thing under the cursor. 
    `,D` does the same, but oppening a new tab.
    - `,o` : find occurrences of the thing under the cursor.
    - `Shift-k` : show docstring of the thing under the cursor.

* **F4**: toggle classes/module browser that lists classes, functions, methods, 
  and such of the current file, and navigates to them when ENTER is pressed.
    
* Error and style checking of code (detects syntax errors, wrong variable names, 
  unused imoprts, pep8 violations, etc). Works on several languages, highlights 
  the erros in the code, at the line number bar, and the status bar. You can open 
  a summarized list of errors with :lwindow .
    
* **Git integration**:
    Icons are shown on each changed line to indicate uncommited changes.
    Ability to jump between changes to current file with `\sn` and `\sp`.
    Useful commands to interact with repos, such as `:Gstatus`, `:Gblame`, `:Glog`, 
    `:Gcommit`, etc. Or simply use :Git with any git command you want to use.
    
* **F2**: toggle pending tasks list (comments in the current file starting 
  with "TODO", "FIXME", etc).
    - `,r` : grep code recursively using Ack!
    - `,wr` : does the same, but searching the current word under the cursor.
    
* **Comment code**:
  - `cc` : comment and uncomment code (current line or selection).

* **Code Snippets**
  Start tipying code and you will see snippets to autocomplete. To list all the code snippet use `Ctrl-t` in insert 
  mode. With `tab` you can select the right snippet to use.

### UI and usability

* Beautiful status line with useful information about file type, encoding, position, git branch 
  and status, errors, etc. When editing python files, it even shows the current function or class.
* F3 : better project browser. You can also open the location of the current file with ,t.

### Other

* Plugins managed using Vim-plug! You can easily install or remove plugins. More info.
* Automatically load .vim.custom configs in your projects when opening vim 
  (it searches all the parent directories until it finds a custom configs file, or the root dir).
* Python interpreter and other shells inside vim using :ConqueTerm python, :ConqueTerm bash, etc. 
  This is Vim specific. NeoVim has its own native alternative.
* Temporary files in better locations, under ~/.vim/dirs (only for Vim, as NeoVim has better default dirs).