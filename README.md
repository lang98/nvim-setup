# nvim-setup

```vim
call plug#begin('~/.vim/plugged')

Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
Plug 'junegunn/fzf.vim'
Plug 'neoclide/coc.nvim', {'branch': 'release'}
Plug 'preservim/nerdtree'
Plug 'Xuyuanp/nerdtree-git-plugin'
Plug 'ryanoasis/vim-devicons'
Plug 'vim-airline/vim-airline'
Plug 'tpope/vim-surround'
Plug 'tpope/vim-repeat'
Plug 'tpope/vim-unimpaired'
Plug 'tpope/vim-eunuch'
Plug 'tpope/vim-sleuth'
Plug 'tpope/vim-commentary'
Plug 'tpope/vim-fugitive'
Plug 'mhinz/vim-signify'
Plug 'mhinz/vim-startify'
Plug 'mhinz/vim-grepper'
Plug 'ajh17/VimCompletesMe'
Plug 'dracula/vim', { 'as': 'dracula' }
Plug 'projekt0n/github-nvim-theme'
Plug 'wincent/terminus'
Plug 'dense-analysis/ale'
Plug 'rust-lang/rust.vim'
Plug 'justinmk/vim-dirvish'
Plug 'psliwka/vim-smoothie'
Plug 'python-mode/python-mode'
Plug 'kassio/neoterm'

call plug#end()

" FZF
" https://github.com/junegunn/fzf#respecting-gitignore
let $FZF_DEFAULT_COMMAND = 'rg --files'

" Ale
let g:ale_fixers = {'rust': ['rustfmt'], 'python': ['autopep8', 'yapf']}
let g:ale_fix_on_save = 1
let g:ale_virtualtext_cursor = 1
let g:ale_completion_enabled = 1

" Neoterm
let g:neoterm_default_mod = 'belowright'
let g:neoterm_size = 16
let g:neoterm_autoinsert = 1

" Startify
let g:startify_change_to_vcs_root = 1

" Dirvish
autocmd FileType dirvish
  \  nnoremap <silent><buffer> t :call dirvish#open('tabedit', 0)<CR>
  \ |xnoremap <silent><buffer> t :call dirvish#open('tabedit', 0)<CR>

" Other setup
let g:python3_host_prog = expand('/usr/bin/python3')

" Settings and mappings
set cursorline
set hidden
set number
set termguicolors
set undofile
set clipboard+=unnamedplus
set showmatch
set incsearch
set ignorecase
set smartcase

colorscheme github_dark

nnoremap <C-l> :noh<CR>
nnoremap <C-p> :Files<CR>
nnoremap <C-j> :Rg<CR>
nnoremap <C-k> :GrepperR

nnoremap <leader>n :NERDTreeFocus<CR>
nnoremap <C-n> :NERDTree<CR>
nnoremap <C-t> :NERDTreeToggle<CR>
nnoremap <C-f> :NERDTreeFind<CR>

nnoremap <silent> gd :ALEGoToDefinition<CR>
nnoremap <silent> gh :ALEHover<CR>
nnoremap <silent> gr :ALEFindReferences<CR>

nnoremap <C-g> :Ttoggle<CR>

```
