### Make Vim as IDE

### Requirements
[Git](http://git-scm.com)

### Use Vundle as plugin manager
#### Install Vundle

```shell
git clone https://github.com/gmarik/vundle vundle_path
```

Different platform has different configurations for **vundle_path**.

On Windows **vundle_path** is $VIM/bundle/vundle. $VIM is the vim installed path. 
On my windows, $VIM is D:\doc\tools. You can use command ```echo $VIM```
to show $VIM in vim command mode.

On Linux or MacOS, **vundle_path** is ~/.vim.

#### Edit your vimrc file
On Windows

``` 
filetype off
set rtp+=$VIM/bundle/vundle
let path='$VIM/bundle'
call vundle#rc(path)
Bundle 'gmarik/vundle'
filetype plugin indent on
``` 

On Linux or MacOS

```
set nocompatible
filetype off
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()
Plugin 'gmarik/vundle'
filetype plugin indent on
```

### Install plugins through Vundle
