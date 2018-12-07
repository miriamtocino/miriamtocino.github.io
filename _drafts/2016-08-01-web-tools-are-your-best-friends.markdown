---
layout: post
title: "Your text editor is your best friend"
date: August 1, 2016
tagline: "2 obstacles to overcome when starting to code"
categories: [tools]
---

![][keyboard-atom-chrome]

You are ready to start. You decided that coding is what makes you happy and you would like to learn how to do it like a pro. Let me give you a pro tip then: mastering your tools will help you get there faster! Life is full of obstacles and when it comes to coding, not feeling comfy with your tools can easily become one.

In this sense, there are two main obstacles that you want to overcome as soon as possible. Look at it as an investment for the rest of your life. It will take some time to get used to them, but stick with it, be patient and trust the process. Let's get started!

> These days I am teaching a ruby course at [Codaisseur](https://www.codaisseur.com/) for a group of people that are learning how to code. This is a special blogpost for all of them, but also for other people that might be in a similar situation.

#### 1. Learn how to type like a pro

If you don't type fast enough

#### 2. Your text editor is your best friend

##### UI (treeview)

---

##### Packages

---

#### Wrapping up

Don't forget that computers are there to help you accomplish something easier. They shouldn't feel like an obstacle. Be aware when something doesn't feel right.




This is the third and last post in this Vim series. You might be interested in reading through my previous posts before you continue reading (especially if you are a real beginner):

* [5 Tips to Survive Your First Week](http://www.miriamtocino.com/articles/5-tips-to-survive-your-first-week)
* [Motions & Command Language](http://www.miriamtocino.com/articles/vim-motions-and-command-language)

In this post we will talk about buffers, tabs, windows and the different modes that you can find in Vim. Let's jump in!

#### Buffers, windows and tabs

If you are moving to Vim from another editor like SublimeText or Atom, you are used to working with tabs in a certain way. Specifically, a tab represents an open file, and as soon as you close it, it goes away. A web browser follows this same principle as well.

Vim has a system for tabs too, but it works in a completely different way from what you are used to. I got quite confused by this when I first started with Vim, so don't panic if that's the case for you as well. You are not alone!

In Vim, there are three levels of view abstraction: **buffers, windows, and tabs**. Let's look at each of them from the ground up, since it's the best way to understand the differences in concept and learn how to use them properly.

##### Buffers

A **buffer** in Vim is an _open instance of a file_. This means that the file may not be visible on the current screen, but it is saved somewhere in memory.

Whenever you open a file in Vim, that file gets put into a buffer that will remain in memory until you explicitly delete it with a call to `:quit` or `:bdelete`. You can list all buffers currently open within a Vim session by typing `:ls`.

Let's look at some other useful commands:

`zz` - Center the current line within the window

`zt` - Bring the current line to the top of the window

`zb` - Bring the current line to the bottom of the window

Although files in Vim's buffer may not be visible at all times, its functionality is analogous to how you use tabs in familiar text editors.

---

##### Windows

A **window** in Vim is a _viewport onto a single buffer_. You can open a new window with `:split` or `:vsplit`, including a filename in the call. This opens your file as a new buffer (again, similar to a tab in a traditional editor) and opens a new window to display it.

This is what a Vim session with multiple windows open (horizontally and vertically) looks like:

[![](http://img.springe.st/20160720-sywxd.png)](http://img.springe.st/20160720-sywxd.png)

Windows are also referred to as _splits_. Let's look at some useful commands:

`:new [filename]` - Open a new window **above** the current window

`:vnew [filename]` - Open a new window **beside** the current window

`:split <filename>` - Edit the specified file in new window **above** the current window

`:vsplit <filename>` - Edit the specified file in a new window **beside** the current window

`<Ctrl-w>h,j,k,l` - Navigate to the window in the given direction

---

##### Tabs

Finally, a **tab** in Vim is a _collection of one or more windows_. This allows you to group windows in a useful way.

Let's look at some related commands:

`:tabnew` - Open a new tab

`:tabedit <filename>` - Edit the file with the provided name in a new tab

`gt` - Go to next tab open

`gT` - Go to previous tab

`<Ctrl-w>T` - Break the current window out to a new tab

#### Modes

Enough about navigation for now. Let's move on and talk about the different **modes** that you will find in Vim's world!

Vim is a "modal" editor, which means it has various modes that change its behavior in response to your key presses. This modal nature is at the core of Vim's power, so it's very important to understand it in order to use Vim in the most efficient way.

Vim has three different modes: **insert, normal** and **visual**. Let's now look at them one at a time.

---

##### Insert Mode

When you use other editors like SublimeText or Atom, you're always working in insert mode. In this mode, characters appear immediately in the buffer as you type them. You can enter insert mode by pressing `i` in normal mode.

However, Vim prioritizes moving through a file and making targeted edits, which are done in normal mode.

---

##### Normal Mode

Normal mode is the **default mode** Vim starts in. You are expected to be in this mode the most of your time, while using all motions and operations that we saw in the [previous post](http://devblog.springest.com/vim-motions-and-command-language).

This fits with the idea that we, as developers, spend the majority of our time moving and editing  within a document, rather than simply adding long blocks of text.

---

##### Visual Mode

In more familiar text editors, a block of text can be selected by clicking the mouse and dragging over a number of lines or characters. Vim introduces _Visual model_, which allows you to reuse all motion commands and operators that there are to manipulate blocks of text.

Enter Visual mode by pressing `v` in normal mode. Move the cursor using all the normal motions, and Vim will highlight from where you started to where you move the cursor. You can use a number of keys such as `d`, `x`, or `c` to operate on the visual selection, similar to how these keys would operate in normal mode.

Sometimes you will need to operate on entire lines. _Visual Line Mode_ turns out to be very useful in these cases, and it can be started by pressing `V` from normal mode.

But what about selecting a column of text? Vim's got you covered too, enter _Visual Block Mode_ by pressing `<Ctrl-v>` from normal mode. Here is a list of the common visual block operations and their mapping:

`d`, or `x` - Delete the visual block selection

`c` - Change the visual block selection

`r` - Replace all characters in the block with the next character you type

`I` - Insert text before the block

`A` - Insert text after the block

_Be aware that when you change or add any new text, Vim will only show the change happening in the first line of the block. After you complete the change/insertion and hit `<esc>`, it will replicate to all lines._

#### Stay Normal

If you only take one thing away from reading this blog post, let it be this: **Normal mode is your best friend!**

Avoid staying in insert mode for extended periods of time. And also, don't move along the file while in insert mode. It might be difficult in the beginning, but once you get used to it, you will see how much faster you become. ;)

#### Wrapping up

This series is a quick introduction to the infinite world of Vim. It is a tool help you get started, but remember that learning Vim is a nonstop continuous process. Stay on it, make it part of your daily life, and every time that you find yourself doing something in a very inefficient way, you know what to do... Go online, look for a friend and ask for help!

[vim-logo]: http://miriamtocino.github.io/images/posts/vim-logo.svg
