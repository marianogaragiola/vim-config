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

