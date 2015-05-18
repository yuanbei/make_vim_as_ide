" An example for a vimrc file.
"
" Maintainer:	Bram Moolenaar <Bram@vim.org>
" Last change:	2014 Feb 05
"
" To use it, copy it to
"     for Unix and OS/2:  ~/.vimrc
"	      for Amiga:  s:.vimrc
"  for MS-DOS and Win32:  $VIM\_vimrc
"	    for OpenVMS:  sys$login:.vimrc

" When started as "evim", evim.vim will already have done these settings.
if v:progname =~? "evim"
  finish
endif

" Use Vim settings, rather than Vi settings (much better!).
" This must be first, because it changes other options as a side effect.
set nocompatible

" Settings For Vundle and plugin list-------------------------{{{
set rtp+=$VIM/bundle/vundle/
call vundle#rc('$VIM/bundle/')
Bundle 'gmarik/vundle'
Bundle 'taglist.vim'
Bundle 'SrcExpl'
Bundle 'Trinity'
Bundle 'scrooloose/nerdtree'
Bundle 'funorpain/vim-cpplint'
Bundle 'protodef'
Bundle 'FSwitch'
Bundle 'Lokaltog/vim-easymotion'
Bundle 'EasyGrep'
Bundle 'sessionman.vim'
Bundle 'a.vim'
Bundle 'Lokaltog/vim-powerline'
Bundle 'tpope/vim-fugitive'
Bundle 'guiniol/vim-showspaces.git' 
Bundle 'jlanzarotta/bufexplorer' 
Bundle 'wincent/command-t' 
Bundle 'Valloric/YouCompleteMe', {'pinned': 1 }
"------------------------------------------------------------}}}
filetype plugin indent on

" allow backspacing over everything in insert mode
set backspace=indent,eol,start
let g:NERDTreeDirArrows=0
if has("vms")
  set nobackup		" do not keep a backup file, use versions instead
else
  set backup		" keep a backup file (restore to previous version)
  set undofile		" keep an undo file (undo changes after closing)
endif
set history=50		" keep 50 lines of command line history
set ruler		" show the cursor position all the time
set showcmd		" display incomplete commands
set incsearch		" do incremental searching
set ts=4
set expandtab
set autoindent
set list
set fileformats=unix

" For Win32 GUI: remove 't' flag from 'guioptions': no tearoff menu entries
" let &guioptions = substitute(&guioptions, "t", "", "g")

" Don't use Ex mode, use Q for formatting
map Q gq

" CTRL-U in insert mode deletes a lot.  Use CTRL-G u to first break undo,
" so that you can undo CTRL-U after inserting a line break.
inoremap <C-U> <C-G>u<C-U>

" In many terminal emulators the mouse works just fine, thus enable it.
set mouse=a

" Open and close all the three plugins on the same time 
nmap <F8>   :TrinityToggleAll<CR> 

" Open and close the srcexpl.vim separately 
nmap <F9>   :TrinityToggleSourceExplorer<CR> 

" Open and close the taglist.vim separately 
nmap <F10>  :TrinityToggleTagList<CR> 

" Open and close the NERD_tree.vim separately 
nmap <F11>  :TrinityToggleNERDTree<CR> 

" Switch syntax highlighting on, when the terminal has colors
" Also switch on highlighting the last used search pattern.
syntax on
syntax enable
set hlsearch

" Only do this part when compiled with support for autocommands.
if has("autocmd")

  " Enable file type detection.
  " Use the default filetype settings, so that mail gets 'tw' set to 72,
  " 'cindent' is on in C files, etc.
  " Also load indent files, to automatically do language-dependent indenting.
  filetype plugin indent on

  " Put these in an autocmd group, so that we can delete them easily.
  augroup vimrcEx
    autocmd!

    " For all text files set 'textwidth' to 78 characters.
    autocmd FileType text setlocal textwidth=78

  " When editing a file, always jump to the last known cursor position.
  " Don't do it when the position is invalid or when inside an event handler
  " (happens when dropping a file on gvim).
  " Also don't do it when the mark is in the first line, that is the default
  " position when opening a file.
  autocmd BufReadPost *
    \ if line("'\"") > 1 && line("'\"") <= line("$") |
    \   exe "normal! g`\"" |
    \ endif

  augroup END

  augroup filetype_vim
    autocmd!
    autocmd FileType vim setlocal foldmethod=marker
  augroup END

else

  set autoindent		" always set autoindenting on

endif " has("autocmd")

" Convenient command to see the difference between the current buffer and the
" file it was loaded from, thus the changes you made.
" Only define it when not defined already.
if !exists(":DiffOrig")
  command DiffOrig vert new | set bt=nofile | r ++edit # | 0d_ | diffthis
		  \ | wincmd p | diffthis
endif

"Map Settings--------------------------------{{{
let mapleader = "-"
nnoremap <leader>sv :source $VIM/vimrc<cr>
nnoremap <c-h> <c-w>h 
nnoremap <c-l> <c-w>l
nnoremap <c-j> <c-w>j
nnoremap <c-k> <c-w>k
"show commandline window
nnoremap <leader>l q:
"Map Settings--------------------------------}}}

"Setting for options -----------------------{{{
set clipboard=unnamed
set number
set colorcolumn=81
set wildmenu
set statusline=%f         
set statusline+=\ -\     
set statusline+=FileType: 
set statusline+=%y        
"-------------------------------------------}}}

"abbrev-----------------------{{{
iabbrev cprt // Copyright 2013 Shenma Co., Ltd.
iabbrev WOW #if defined(WOW_BUILD) <cr>#endif
iabbrev inc #include ""<esc>h
iabbrev TODO // TODO(yuanbei.clj): 
"-----------------------------}}}

"Setting for vim-cpplint---------{{{
autocmd FileType cpp map <buffer> <F3> :call Cpplint()<CR>
"Settings for vim-cpplint--------}}}
"settings for FSwitch--------------------{{{
 augroup mycppfiles
   au!
   au BufEnter *.h,*cc,*cpp let b:fswitchdst  = 'cpp,cc,C'
   au BufEnter *.h,*cc,*cpp let b:fswitchlocs = 'reg:/include/src/,reg:/include.*/src/'
 augroup END
 nnoremap <silent> <Leader>of :FSHere<cr>
"settings for FSwtich--------------------}}}
"Settings for theme----------------------{{{
set background=dark
colorscheme molokai
syntax enable
let g:molokai_original = 1
"Settings for theme----------------------}}}
"Settings for clang-format---------{{{
nnoremap <C-F> :pyfile C:\Program Files (x86)\LLVM\share\clang\clang-format.py<CR>
"Settings for clang-format---------}}}
"Settings for ycm----------{{{
nnoremap <leader>jd :YcmCompleter GoTo<CR>
"Settings for ycm----------}}}
"Settings for BufExplorer----{{{	
nnoremap <leader>bf :BufExplorer <CR>
"Settings for BufExplorer----}}}
"Settings for path--------{{{
set path=F:\work_dir_new\release\src;F:\work_dir_new\ucproxy\src;H:\regular-m41.0.2250.2\src
"Settings for path--------}}}
"Settings for ShowSpaces-----{{{
let b:showSpaces = 1
"Settings for ShowSpaces-----}}}
"Settings for Command-T----{{{
nnoremap <silent> <leader>ct :CommandT<CR>
nnoremap <silent> <leader>cbf :CommandTBuffer<CR>
nnoremap <silent> <leader>cm :CommandTMRU<CR>
let g:CommandTMaxFiles=20000
let g:CommandTMaxDepth=20
let g:CommandTTraverseSCM='pwd'
let g:CommandTMaxCachedDirectories=0
"Settings for Command-T----}}}
"Settings for a.vim----{{{
nnoremap <silent> <leader>a :A<CR>
"Settings for a.vim----}}}
"Settings for protodef----{{{
let g:disable_protodef_mapping = 1 
let g:disable_protodef_sorting = 1
nnoremap  <silent> <leader>s :set paste<cr>i<c-r>=protodef#ReturnSkeletonsFromPrototypesForCurrentBuffer({})<cr><esc>='[:set nopaste<cr>
nnoremap  <silent> <leader>sn :set paste<cr>i<c-r>=protodef#ReturnSkeletonsFromPrototypesForCurrentBuffer({'includeNS' : 0})<cr><esc>='[:set nopaste<cr>
"Settings for protodef----}}}
"Settings for fugitive----{{{
autocmd QuickFixCmdPost *grep* cwindow
"Settings for fugitive----}}}
