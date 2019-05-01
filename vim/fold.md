> This page of tutorial is from https://unix.stackexchange.com/a/336537 

# Fold by default

Vim's default folding method is `manual` meaning that the folds are created manually; otherwise, there is no fold to be closed or opened using <kbd>z</kbd><kbd>a</kbd>, <kbd>z</kbd><kbd>o</kbd>, or <kbd>z</kbd><kbd>c</kbd> as you described. But, you can create a fold by <kbd>z</kbd><kbd>f</kbd>`{motion}` in *Normal* mode or <kbd>z</kbd><kbd>f</kbd> in *Visual* mode; e.g. <kbd>z</kbd><kbd>f</kbd><kbd>j</kbd> creates a fold for current line and the next following one in *Normal* mode.

# Fold by `indent`

The accepted answer, by @Anthon, describes how to set folding method to `indent`; i.e. folding are defined by the level of indentations.

# Fold by `syntax`

In a more convenient way, folds can be created automatically based on the language syntax of the current buffer. If you are using a programming language, let's call it _L_, and you have folding definition of _L_ (e.g. you have installed a Vim plugin in which the folding information of _L_ is defined; such as _[c.vim]_ for C/C++, or _[python-mode]_ for Python), you just need to set folding method to `syntax`:

```vim
set foldmethod=syntax
```

That's it. The most useful commands for working with folds are:

- <kbd>z</kbd><kbd>o</kbd> opens a fold at the cursor.
- <kbd>z</kbd><kbd>Shift</kbd>+<kbd>o</kbd> opens all folds at the cursor.
- <kbd>z</kbd><kbd>c</kbd> closes a fold at the cursor.
- <kbd>z</kbd><kbd>m</kbd> increases the `foldlevel` by one.
- <kbd>z</kbd><kbd>Shift</kbd>+<kbd>m</kbd> closes all open folds.
- <kbd>z</kbd><kbd>r</kbd> decreases the `foldlevel` by one.
- <kbd>z</kbd><kbd>Shift</kbd>+<kbd>r</kbd> decreases the `foldlevel` to zero -- all folds will be open.

[c.vim]: http://vimawesome.com/plugin/c-vim-the-thing-itself
[python-mode]: http://vimawesome.com/plugin/python-mode