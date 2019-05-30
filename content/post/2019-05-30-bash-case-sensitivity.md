---
title: Case-insensitive Completion in Bash
author: Riku Takei
date: '2019-05-30'
slug: "case-insensitive-bash"
categories: ["bash"]
tags: ["bash","tips"]
---

Have you ever been annoyed by having to re-type a file you are looking for,
just because the filename contains capital letter(s)?

Tab-completion can get you closer to the correct filename without knowing what
the actual filename is, but it’s not quite smart enough to account for
uppercase and lowercase letters (i.e. it’s case-sensitive).

For example, if you type `coolfile` and hit tab to complete the filename
`coolFile.txt`, tab-completion won’t work.

If you want to change this behaviour so you can type the filename without
thinking about the casing, then add these lines to your `~/.inputrc` file (or if
you don’t have one already, create it and add the following):

``` bash
$include /etc/inputrc
set completion-map-case On
set completion-ignore-case On
```

`completion-ignore-case` option allows you to complete filenames, ignoring the
casing.

`completion-map-case` option allows you to do something similar, but with
hyphens and underscores (i.e. `-` and `_` are now equivalent).

After you have added these and restart your terminal, you should be able to
tab-complete files without worrying about casing or hyphens/underscores.

