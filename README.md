# ProjectLocal - .vimrc files for your project

ProjectLocal lets you set up project-specific `.vimrc` files.

When you edit a file, it searches up through your directories, looking for a `.vimrc` file. It tries to guess the project's root by looking for a `.stop_traversal/.git/.hg` folder on the way up.

## Status

Stable. Feature-complete, so there's no new development, but any bugs will be fixed if found.

## Installation

* Install [Pathogen][pathogen]. (You're already using Pathogen, right?)
* Clone this project into `~/.vim/bundle/vim-projectlocal`.
* Add a `.vimrc` to the root of your project.

## Customization

ProjectLocal will also look for `.vimrc` files in your subdirectories. For example:

```
.vimrc              => Affects all files in the project.
resources/.vimrc    => Affects any file under resources/
resources/js/.vimrc => Affects any file under resources/js/
```

Files are processed in top-down order.

By default, files called `.stop_traversal` and directories called `.git` or `.hg` mark the root of a project. You can customize this by changing the setting in your main `~/.vimrc`:

```vim
" The root is considered to be the first directory containing an item with one of these names:
let g:projectlocal_project_markers = ['.stop_traversal', '.git', '.hg', '.project', 'README.md']
```

## Credits
Thanks to Steve Losh for his excellent guide to Vimscript, [Learn Vimscript the Hard Way][learnvim], and [VimNinjas][vimninjas] for the inspiration.

[pathogen]: https://github.com/tpope/vim-pathogen/
[learnvim]: http://learnvimscriptthehardway.stevelosh.com/
[vimninjas]: http://www.vimninjas.com/
