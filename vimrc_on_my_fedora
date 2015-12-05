set nocompatible
filetype off

set rtp+=~/.vim/bundle/vundle/
call vundle#rc()
Plugin 'gmarik/vundle'

filetype plugin indent on  

let g:NERDTreeDirArrows=0

Bundle 'taglist.vim'
Bundle 'wesleyche/SrcExpl'
Bundle 'wesleyche/Trinity'
Bundle 'scrooloose/nerdtree'
Bundle 'Lokaltog/vim-easymotion'
Bundle 'a.vim'
Bundle 'Lokaltog/vim-powerline'
Bundle 'tpope/vim-fugitive'
Bundle 'jlanzarotta/bufexplorer' 
Bundle 'Yggdroot/LeaderF'
Bundle 'Valloric/YouCompleteMe'
Bundle 'wannesm/wmgraphviz.vim'
Bundle 'andviro/flake8-vim'

set clipboard=unnamed
let mapleader = "-"
set mouse=a

syntax on
syntax enable
set hlsearch

nnoremap <leader>sv :source $HOME/.vimrc<cr>

"Setting for options -----------------------{{{
set clipboard=unnamed
set number
set colorcolumn=81
set wildmenu
set statusline=%f         
set statusline+=\ -\     
set statusline+=FileType: 
set statusline+=%y        
set number
set list
"-------------------------------------------}}}
nnoremap <leader>8 :TrinityToggleAll<CR>
nnoremap <leader>9 :TrinityToggleSourceExplorer<CR>
nnoremap <leader>10 :TrinityToggleTagList<CR>
nnoremap <leader>11  :TrinityToggleNERDTree<CR>
nnoremap <leader>3  :PyFlake<CR>
nnoremap <leader>4  :PyFlakeAuto<CR>
nnoremap <c-h> <c-w>h
nnoremap <c-j> <c-w>j
nnoremap <c-k> <c-w>k
nnoremap <c-l> <c-w>l

nnoremap <silent> <leader>a :A<CR>
nnoremap <leader>bf :BufExplorer <CR>
"Settings for encoding
set fileencodings=utf-8,gb2312,latin-1
"set termencoding=utf-8
"set encoding=utf-8

"Settings for fugitive----{{{
autocmd QuickFixCmdPost *grep* cwindow
"Settings for fugitive----}}}
"Settings for theme----{{{
syntax enable
"Settings for theme----}}}
"Settings for ycm----------{{{
nnoremap <leader>jd :YcmCompleter GoTo<CR>
"Settings for ycm----------}}}
"Settings for flak8-------{{{
let g:PyFlakeOnWrite = 1
let g:PyFlakeCheckers = 'pep8,mccabe,pyflakes'
let g:PyFlakeDefaultComplexity = 10
"let g:PyFlakeDisabledMessages = 'E501'
let g:PyFlakeCWindow = 6
let g:PyFlakeSigns = 1
let g:PyFlakeMaxLineLength = 100
let g:PyFlakeRangeCommand = 'Q'
"Settings for flak8-------}}}
