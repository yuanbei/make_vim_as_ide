#This is my vim settings on different platforms.

#How to use vundle as plugin manager of vim

###
1. Install [Git](http://git-scm.com) on your windows system. Add Git's bin path on your system PATH.

###
2. Install Vundle.
```git
  git clone https://github.com/gmarik/vundle $VIM/bundle/vundle
```
  $VIM is the vim installed path. In my windows ,$VIM is D:\doc\tools.
  You could use command 'echo $VIM ' to show $VIM in vim command mode.

###
3. Edit your vimrc file.

```vimscript 
  filetype off
  set rtp+=$VIM/bundle/vundle
  let path='$VIM/bundle'
  call vundle#rc(path)
  Bundle 'gmarik/vundle' 
  filetype plugin indent on  
``` 

After this settings, Vundle has been installed sucessfully.
