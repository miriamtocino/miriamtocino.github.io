---
layout: post
title: "Vim: Motions & Command Language"
date: July 26, 2016
tagline: "Learning how to move, jump and edit"
tags : [vim]
---

![][vim-logo]

This is the second post in the vim series. You might be interested in reading through my previous post before you continue reading (especially if you are a real beginner):

* [5 Tips to Survive Your First Week](http://www.miriamtocino.com/articles/5-tips-to-survive-your-first-week)

In this post we will dive into some subjects that you need to master when working with Vim. The very first one is motions, also known as _how to get your cursor where you want it_.

#### Motions and Moving

Developers spend a lot of time navigating files and positioning the cursor where needed, and not much time typing new code. It comes as no surprise that Vim is optimized for this situation and has many ways to efficiently move the cursor where you want it.

Motions are defined as the commands you use to move around Vim.

##### Moving within a line

These are the most important key bindings for moving within a line:

`h`, `l` - move left/right by character

`w` - move forward one (**w**)ord

`b` - move (**b**)ackward one word

`e` - move forward to the (**e**)nd of a word

---

_Before we move forward, let me give you a pro tip: Whenever you find yourself repeating or holding down a motion key to move around, take a second to consider if there is a better way of doing what you are trying to accomplish. Most probably there is one ;-)_

##### Jumping within a line

But what if you want to move to a specific character within a line? Try any of these:

`f<char>` - (**f**)ind a character forward in a line and move to it

`T<char>` - find a character backward in a line and move un(**t**)il it

`t<char>` - find a character forward in a line and move un(**t**)il it (one character before)

`F<char>` - (**f**)ind a character backward in a line and move to it

`$` - go to the end of the line

`0` - go to the beginning of the line

---

##### Moving between lines

I know, I know... most of the files you work with contain more than one line! So here it is: How to move between different lines:

`j`, `k` - move up/down one line

`H`, `M`, `L` - move (**H**)igh, (**M**)iddle, or (**L**)ow within the viewport

`Ctrl-u`, `Ctrl-d` - move (**u**)p or (**d**)own

`/` - search for any word in the file

`n` - repeat last search

`N` - repeat last search in opposite direction

`<NN>G` - (**G**)o to the line number NN

`G` - go to the end of the file

`gg` - go to the beginning of the file


#### Command Language

Enough movement for now! Next let's focus on one of the most powerful and unique aspects of Vim: **Vim's Command Language**. Vim uses a concise and expressive language of key mappings that allows us to describe every edit we want to make. And it is worth investing the time needed to master it!

##### Editing Command Syntax

Just as any sentence is made up of a verb and a noun, an editing command is made up of two parts: **an operation and a section of text**. For example, take the commands for "delete this word", "change the next sentence" or "copy this paragraph". They all have the same structure:

`<number><command><text object or motion>`

1. The **number** is used to perform the command over multiple text objects or motions, e.g., backward three words, forward two paragraphs. This number is optional and can appear either before or after the command.

2. The **command** is an operation, e.g., change, delete (cut) or yank (copy).

3. The **text object** or **motion** can either be a text construct, e.g., a word, a sentence, a paragraph, or a motion, e.g., forward a line, back one page, end of the line.

Let's look at each of these one at a time.

---

##### Commands

Find below some of the most useful operator mappings:

`d` - (**D**)elete

`c` - (**C**)hange

`y` - (**Y**)ank or copy

`>`, `<` - indent, dedent

`=` - reformat (reindent, break long lines, etc.)

The simplest commands are made by repeating the operator a second time to act on the current line. For example, where `d` is the operator for _delete_, `dd` will delete the whole line. Each of `yy`, `cc`, `>>`, `==` behave similarly.

---

##### Using Motions

We can also identify text by using any **motion**. Just like you can use `w` to move to the next word, you can use `dw` to delete to the next word. This also includes more complex motions such as `t`, which will wait for you to specify a character to go up un(**t**)il.

Herein lies the magic of Vim: Just by following these rules, you can create any variation of the delete operation by combining it with any motion. Let's look at some examples:

`dw` - delete to the next word

`dt,` - delete up until the next comma on the current line

`de` - delete to the end of the current word

`d2e` - delete to the end of next word

`dj` - delete down a line (current and one below)

`dt)` - delete up until next closing parenthesis

`d/rails` - delete up until the first search match for "rails"

---

##### Using Text Objects

You can think of text objects as a kind of "noun" that can be used in place of motions to define a range of text from anywhere within it. Let's look at some examples:

`iw`, `aw` - inner word, a word

`ip`, `ap` - inner paragraph, a paragraph

`i)`, `ap` - inner parenthesis, a parenthesis

`i'`, `a'` - inner single quote

`i"`, `a"` - inner double quote

`it`, `at` - inner tag, a tag

Check out [this blogpost](http://blog.carbonfive.com/2011/10/17/vim-text-objects-the-definitive-guide/) for a nice rundown of the different text objects available and practical examples.

You can also get a full listing from within Vim by typing `:h text-objects`.

By now you might be wondering if there are any best practices to help you decide when to use motions and when to use text objects. A command using a motion, for example `cw`, operates from the current cursor position. A command using a text-object, for example `ciw`, operates on the whole object regardless of the cursor position. Although this requires one more character, it saves you the time and effort of moving the cursor into the "right" position.

That's why it's generally accepted that you should try to use text objects rather than motions whenever possible.

#### Wrapping up

Are you still curious about the infinite world of Vim? In the next post I will focus on windows and tabs, modes and plugins. So stay tuned!

[vim-logo]: http://miriamtocino.github.io/images/posts/vim-logo.svg
