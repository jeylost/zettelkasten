---
tags:
  - bash
---
If you're using bash, try the `edit-and-execute-command` command. By default, this is assigned to `Ctrl-x Ctrl-e` (type ctrl-x, then ctrl-e).

This should open whatever editor is specified in your environment. Whatever is in the buffer when you exit will execute in the shell - including multiple-line commands.

Unfortunately [fish shell](https://fishshell.com/) doesn't support