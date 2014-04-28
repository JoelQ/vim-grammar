# Vim Grammar: Commands, Motions and Text Objects

---

# Cryptic Commands

`^c8awThis `

> However, due to unknown causes, this would ...
> This would ...


## ???


## Vim has grammar, just like English


## Simple English Grammar

`<subject> <verb> <object>`

> I love Vim


## Simple Vim Grammar

`<command> <motion>`

`dw` (delete word)


## Motions

Move your cursor


## Common motions

* `h`, `j`, `k`, `l` just like the arrow keys
* `^` beginning of line
* `$` end of line (think regex)


## Common Vim commands

* `d` Delete (also cut)
* `c` Change
* `y` Yank (copy)


## Double commands automatically run on the current line

* `dd` Delete the current line
* `cc` Change current line
* `yy` Yank current line


## Combining commands and motions

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

* `w` word
* `s` sentence
* `p` paragraph
* `tag`


## Two ways to refer to a text object

* `i<text object>` inner text object, without surrounding whitespace
* `a<text object>` around text object, including surrounding whitespace


## Text objects can't be used by themselves


## Combining with commands and modifiers

`<command> <modifier> <text object>`

* `dap` delete around paragraph: delete paragraph including surrounding
  whitespace

* `d2as` delete around two sentences


## Delimiters as text objects

`ci(` change inner parenthesis
`ci"` change inner double quotes


## Back to our original problem

* `c8aw` delete 8 words and surrounding whitespace and drop into insert mode
* `This ` type the word "This "

---

# Joël Quenneville

* Github: @JoelQ
* Twitter: @joelquen
