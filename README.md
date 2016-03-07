Kurt's vimrc
============
Author: Kurt Hsu (kurt.hsu@gmail.com)

Forked from vgod's vimrc https://github.com/vgod/vimrc.

ONE-STEP INSTALL
----------------

Use curl (for Mac OS X):

     curl -o - https://raw.githubusercontent.com/kurthsu/vimrc/master/auto-install.sh | sh

or wget (for most UNIX platforms):

     wget -O - https://raw.githubusercontent.com/kurthsu/vimrc/master/auto-install.sh | sh


MANUALLY INSTALL
----------------

1. Check out from github

        git clone git://github.com/kurthsu/vimrc.git ~/.vim
        cd ~/.vim
        git submodule update --init --recursive

2. Install ~/.vimrc and ~/.gvimrc

        ./install-vimrc.sh

3. (Optional, if you want Command-T) Compile the Command-T plugin

        cd .vim/bundle/command-t/ruby/command-t
        ruby extconf.rb
        make

MANUALLY INSTALL ON WINDOWS
---------------------------

1. Check out from github

        cd C:\Program Files\Vim   (or your installed path to Vim)
        rmdir /s vimfiles         (This deletes your old vim configurations. If you want to keep it, use move instead of rmdir.)
        git clone git://github.com/kurthsu/vimrc.git vimfiles
        git submodule update --init

2. Install vimrc. Add the following line at the end of C:\Program Files\Vim\vimrc.

        source $VIM/vimfiles/vimrc


INSTALL & UPGRADE PLUGIN BUNDLES
--------------------------------

All plugins (except vim-latex) were checked out as git submodules, 
which can be upgraded with `git pull`. For example, to upgrade Command-T 

     cd ~/.vim/bundle/command-t
     git pull

To install/update/remove a new plugin as a git submoudle, type the following commands.

     cd ~/.vim
     // add a new bundle
     git submodule add [GIT-REPOSITORY-URL] bundle/[PLUGIN-NAME]

     // or remove a bundle
     git submodule deinit [PLUGIN-NAME]
     git rm [PLUGIN-NAME]
     rm -rf .git/modules/[PLUGIN-NAME]

     // or update all bundles
     git submodule foreach git pull origin master

PLUGINS
-------

Utility

* [Pathogen](http://www.vim.org/scripts/script.php?script_id=2332): Pathogen let us install a plugin as a bundle in ~/.vim/bundle seprately.

* [NerdTree](http://www.vim.org/scripts/script.php?script_id=1658): A tree explorer plugin for navigating the filesystem.
  Useful commands:
    `:Bookmark [name]` - bookmark any directory as name
    `:NERDTree [name]` - open the bookmark [name] in Nerd Tree

* [NerdCommenter](http://www.vim.org/scripts/script.php?script_id=1218): <leader>cc to comment, <leader>cu to uncomment. <leader>c<space> to toggle.

* [AutoPair](http://www.vim.org/scripts/script.php?script_id=3599): Insert or delete brackets, parens, quotes in pair. an
* [Command-T](https://github.com/wincent/Command-T): Provide an extremely fast "fuzzy" mechanism for opening files and buffers with a minimal number of keystrokes. Open and navigate between files with `cmd-t`.

* [vim-surround](https://github.com/tpope/vim-surround/blob/master/doc/surround.txt): deal with pairs of surroundings.

  * `ysiw` (you surround in word)
  * `cs` (change surround)
  * `ds` (delete surround)
  * `S` (surrond in visual mode)

* [YankRing](http://www.vim.org/scripts/script.php?script_id=1234): Maintains a history of previous yanks, changes and deletes

  * `:YRShow` - Display the contents of the yankring.
  * `<C-P>` - Move backwards through the yankring.
  * `<C-N>` - Move forwards through the yankring.

* [xmledit](http://www.vim.org/scripts/script.php?script_id=301): XML/HTML tags will be completed automatically.

* [vim-multiple-cursors](https://github.com/terryma/vim-multiple-cursors): True Sublime Text style multiple selections for Vim.

* [matchit](http://www.vim.org/scripts/script.php?script_id=39): extended % matching for HTML, LaTeX, and many other languages.

* [SuperTab](http://www.vim.org/scripts/script.php?script_id=1643): Do all your insert-mode completion with Tab.

* [EasyMotion](https://github.com/Lokaltog/vim-easymotion): An easy way to jump to a word.

  * `,,w` - forward EasyMotion
  * `,,b` - backward EasyMotion

* [TagBar](http://majutsushi.github.com/tagbar/): browsing the tags of source files ordered by classes.

  * `F7` toggles the TagBar

* [Taglist](https://github.com/vim-scripts/taglist.vim/blob/master/doc/taglist.txt): taglist, list functions, structures. <F8> to toggle.

* [Indent Motion](https://github.com/vim-scripts/indent-motion): Vim motions to the start and end of the current indentation-delimited block
  Useful commands:
  * `,]` - Move to the end of the current indentation-delimited block (very useful in Python and CoffeeScript)
  * `,[` - Move to the beginning of the current indentation-delimited block (very useful in Python and CoffeeScript)

* [TLibVim](https://github.com/tomtom/tlib_vim): Provide some utility functions. There isn't much need to install it unless another plugin requires you to do so.

* [Addon-mw-utils](https://github.com/MarcWeber/vim-addon-mw-utils): Depended library for SnipMate.

* [SnipMate](http://www.vim.org/scripts/script.php?script_id=2540): TextMate-style snippets for Vim.

* [SnipMate-Snippets](https://github.com/scrooloose/snipmate-snippets): A collection of snippets for snipmate.

* [ack.vim](https://github.com/mileszs/ack.vim): run ack (a better grep) from vim, and shows the results in a split window.

* [Airline](https://github.com/vim-airline/vim-airline): Lean & mean status/tabline for vim that's light as air.

  * `:Ack [options] {pattern} [{directory}]`

* [Syntastic](https://github.com/scrooloose/syntastic): A syntax checking plugin for Vim that runs files through external syntax checkers and displays any resulting errors to the user.

* [Multiple-Cursors](https://github.com/terryma/vim-multiple-cursors): True Sublime Text style multiple selections for Vim. Ctrl + n to multiple select, v to enter visual mode, i to enter insert mode.

* [Ctrlp](https://github.com/ctrlpvim/ctrlp.vim): Fuzzy finder. <leader>f to search. Ctrl + x (sp), Ctrl + v (vsp), Ctrl + t (tab)

* [ag.vim](https://github.com/rking/ag.vim): Vim plugin for the_silver_searcher, 'ag', a replacement for the Perl module / CLI script 'ack'

  * `:Ag [options] {pattern} [{directory}]`: Search recursively in {directory} (which defaults to the current directory) for the {pattern}.

* [gruvbox](https://github.com/morhetz/gruvbox): Retro groove color scheme for Vim

  * `:set background=dark | light`

C/C++ Support

* [OmniCppComplete](http://www.vim.org/scripts/script.php?script_id=1520): C/C++ omni-completion with ctags database.

Python Support

* [PythonComplete](http://www.vim.org/scripts/script.php?script_id=1542): Python omni-completion.

* [iPython-Vim](https://github.com/ivanov/vim-ipython): A two-way integration between Vim and IPython.

JavaScript Support

* [JavaScriptSyntax](https://github.com/jelera/vim-javascript-syntax): Support JavaScript syntax.

* [JSIndent](https://github.com/jason0x43/vim-js-indent): Vim indenter for standalone and embedded JavaScript

* [YouCompleteMe](https://github.com/Valloric/YouCompleteMe): A fast, as-you-type, fuzzy-search code completion engine for Vim.

* [TernForVim](https://github.com/ternjs/tern_for_vim): Provide Tern-based JavaScript editing support.

Golang Support

* [vim-go](https://github.com/fatih/vim-go): Go development plugin for Vim

  * `:GoDef` - Go to symbol/declaration
  * `:GoDoc` - Look up documentation with :GoDoc inside Vim or open it in browser
  * `:GoBuild/Install/Test` - Compile your package with :GoBuild, install it with :GoInstall or test them with :GoTest (also supports running single tests via :GoTestFunc)
  * `:GoRun` - Quickly execute your current file/files with :GoRun
  * `:GoPath` - Change or display GOPATH with :GoPath
  * `:GoCoverage` - Create a coverage profile and display annotated source code in browser to see which functions are covered with :GoCoverage

* [gocode](in YouCompleteMe)(https://github.com/nsf/gocode): An autocompletion daemon for the Go programming language

* [gotag](https://github.com/jstemmer/gotags): ctags-compatible tag generator for Go

```
    gotags [options] file(s)
    -L="": source file names are read from the specified file. If file is "-", input is read from standard in.
    -R=false: recurse into directories in the file list.
    -f="": write output to specified file. If file is "-", output is written to standard out.
    -silent=false: do not produce any output on error.
    -sort=true: sort tags.
    -tag-relative=false: file paths should be relative to the directory containing the tag file.
    -v=false: print version.
```

Git

* [GitGutter](https://github.com/airblade/vim-gitgutter): shows a git diff in the 'gutter' (sign column). It shows whether each line has been added, modified, and where lines have been removed.

License
-------

This vimrc project is released under [Creative Commons Attribution-ShareAlike 3.0 Unported License](http://creativecommons.org/licenses/by-sa/3.0/deed.en_US).

