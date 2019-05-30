---
title: Using `less` more effectively
author: Riku Takei
date: '2019-05-29'
slug: "use-less-effectively"
categories: ["bash"]
tags: ["bash","less","man"]
---

If you've ever used `bash` terminal before, you would have come across the
`less` command at some point.

For anyone who is not familiar with `less`, `less` is a "paging" command that
allows you to view file(s) of interest on your terminal. It is usually the
default "pager" (program used to view a document) for a terminal environment
that comes with your Unix/Linux operating system.

Now, you might ask "why bother using `less` when you can open it up on a text
editor, or even better, point and click on the file"?

The key difference is that `less`-like paging program reads and displays only
the required information that can fit on a single screen. In other words, it
will only read in a small portion of the file at a time.

This allows you to load the file (or part of the file) very quickly, whereas
other programs will try and read the whole file first and then display the
first part of the file.

This is extremely helpful when you need to quickly view large text-based data
such as VCF, which can get into tens to hundreds of GB in size -- and trust me,
your computer won't like handling that sort of data with a notepad program and
the likes.

------

## Move FASTER!!!

Now, on to the main part of this blog post: how to use `less` more effectively.
Arrow keys and space bar are fine to begin with, but there are better ways to
move around in `less`. Here are some of the ways you can speed up:

| Keys             |                                         |
| :--------------: | --------------                          |
| `j`              | Move down one line (same as down arrow) |
| `k`              | Move up one line (same as up arrow)     |
| `d`              | Move forward half window                |
| `u`              | Move backward half window               |
| `f`              | Move forward one window (same as space) |
| `b`              | Move backward one window                |
| `g`              | Move to the first line of the file      |
| `G`              | Move to the last line of the file       |

-----

Easiest way to remember the `d/u/f/b` keys is to remember it as Down, Up,
Forward, and Backward.

Another use of `G` is to skip to a specific line by typing the line number
before pressing `G` (e.g. typing `150G` in `less` will skip to line 150 of the
file currently open).

Now, if you want to search within the file for a certain word, use these keys:

| Keys             |                                                    |
| :--------------: | --------------                                     |
| `/PATTERN`       | Search forward in the file for a matching PATTERN  |
| `?PATTERN`       | Search backward in the file for a matching PATTERN |
| `n`              | Skip forward to the next match in the file         |
| `N`              | Skip backward to the next match in the file        |

-----

So, for example, if you open up a manual page for a particular command with
`man`, and you wanted to know what a certain flag does (e.g. `-x` option), then
you could type `/-x` followed by enter, and it will skip to the first line that
matches `-x`. After that, you could press the `n` or `N` keys to go back
and forward to the lines that matched your search.

-----

## Some useful options of `less`

A couple of flags/options I want to touch on are the `-S` and the `-N`.

`-S` will cut or truncate any long lines that run off the screen, instead of
the default behaviour of wrapping the line around.

`-N` will number the lines when you open up a file with `less`, so you know
which part of the file you are looking at.

Now, if you provide a line number with a `+` before you run `less`, it will
open the file at that particular line of the file.

For example, the following command will open up `my_file.txt` at line 5,
truncating any long lines that go over the terminal screen:

``` bash
less -N -S +5 my_file.txt
```

-----

All of this information is on a quick summary of `less` which you can open by
pressing the `h` key while in `less`, or by using `man less` to view the
documentation (with `less`!).

