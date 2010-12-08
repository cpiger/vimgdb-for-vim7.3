
About this patch
**************
This is a vim(v7.3) patch to provide Gdb support within Vim,
It's modified from vimgdb72-1.14 (http://clewn.sourceforge.net/)

Introduction
**************
The patch vimgdb implements full gdb support in the vim editor: breakpoints, watch variables, 
gdb command completion, assembly windows, etc.


vimgdb install
**************
a) You need:

vim-7.3.tar.bz2                 http://www.vim.org/sources.php 

vimgdb-for-vim7.3 (this patch)   https://github.com/larrupingpig/vimgdb-for-vim7.3 

b) Untar all files, apply the patch and make Vim:

tar xjvf  vim-7.3.tar.bz2  -C /tmp

tar xzvf  vimgdb-for-vim7.3.tar.gz  -C /tmp

cd /tmp

patch  -p0 < vimgdb-for-vim7.3/vim73.patch

cd vim73/src

make

sudo make install

IMPORTANT NOTE: you must run make (not ./configure), and if you run
./configure then you must add the --enable-gdb command line argument
in order to include the gdb feature (vimgdb) in vim.


c) Install vimGdb runtime:

Copy the file vimgdb_runtime found in the vimgdb tarball, to your
runtime path. To find your runtime path location execute the vim
command (this is usually $HOME/.vim): 
:set runtimepath?

cp  -rf /tmp/vimgdb-for-vim7.3/vimgdb_runtime/*  ~/.vim

Change to the doc directory, start Vim and run the ":helptags ."
command to process the taglist help file. Without this step, you
cannot jump to the taglist help topics. You can now use the ":help
vimgdb" command to get the vimGdb documentation.




