# Vim Grammar

Commands, Motions and Text Objects

---

# Cryptic Commands

`cit<td>Value</td><ESC>llci</tr<ESC>^ci<tr`

* Before: `<li>Value</li>`
* After: `<tr><td>Value</td></tr>`


## ???

![confused cat](images/confused.jpg)


## Vim has grammar, just like English


## Simple English Grammar

`<subject> <verb> <object>`

> I love Vim


## Simple Vim Grammar

`<command> <motion>`

`dw` (delete word)

---

# Motions

Move your cursor


## Common motions

* `h`, `j`, `k`, `l` just like the arrow keys
* `^` beginning of line
* `$` end of line (think regex)


## Words

* `w` move forward one word
* `b` move to beginning of word
* `e` move to end of word


## Visual mode

Slow, can be a crutch

---

## Common Vim commands

* `d` Delete (also cut)
* `c` Change
* `y` Yank (copy)
* `=` Auto-indent
* `<`/`>` Indent left/right


## Double commands

* `dd` Delete the current line
* `cc` Change current line
* `yy` Yank current line


## Combos

* `d$` Delete till the end of the line
* `c^` Change till the beginning of the line
* `dj` Delete the current line and the one below


## Composite motions

* `t<char>` till character (excluding character)
* `f<char>` find character


## Can be combined with a command

* `dtl` Delete till the `l`
* `cfe` Change up to (and including) `e`

---

# Modifiers


## When you need more than one

`<command> <modifier> <motion>`

* `d3j` Delete the current line and 3 lines below it
* `d4t)` Delete till the fourth parenthesis

---

# Text Objects


## Representing text concepts

* `iw`/`aw` inner/around word
* `is`/`as` inner/around sentence
* `ip`/`ap` inner/around paragraph
* `it`/`at` inner/around tag


## Text objects can't be used by themselves


## Text objects don't require your cursor to be at the beginning


## Combining with commands and modifiers

`<command> <modifier> <text object>`

* `dap` delete around paragraph: delete paragraph including surrounding
  whitespace

* `d2as` delete around two sentences


## Delimiters as text objects

`ci(` change inner parenthesis
`ci"` change inner double quotes

---

## Back to our original problem

`cit<td>Value</td><ESC>llci</tr<ESC>^ci<tr`

* Before: `<li>Value</li>`
* After: `<tr><td>Value</td></tr>`


## Adding `<td>`

`cit<td>Value</td><ESC>`

Change contents of tag to `<td>Value</td>`, return to normal mode


## Changes

* Before: `<li>Value</li>`
* After: `<li><td>Value</td></li>`


## Closing `<li>`

`llci</tr<ESC>`

Move right two characters, change the contents of the angle brackets to `/tr`,
return to normal mode


## Changes

* Before: `<li><td>Value</td></li>`
* After: `<li><td>Value</td></tr>`


## Opening `<li>`

`^ci<tr`

Move to the beginning of the line, change to contents of the angle brackets to
`tr`


## Changes

* Before: `<li><td>Value</td></tr>`
* After: `<tr><td>Value</td></tr>`

---

# Extending your vocabulary

Adding more verbs and nouns


## Commands

* `tpope/vime-commentary` comments out the given text object


## Text objects

* `nelstrom/vim-textobj-rubyblock` ruby blocks
* `michaeljsmith/vim-indent-object` indentation level

---

# Joël Quenneville

* Github: @JoelQ
* Twitter: @joelquen
* Slides: https://github.com/JoelQ/vim-grammar
* Cheat sheet: https://github.com/JoelQ/vim-grammar/blob/master/cheat_sheet.md
