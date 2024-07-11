---
tags:
  - vim
  - editor
  - development_environment
---
# Vim Commands
This is a list of vim commands that I'm using on my daily basis:
cd - command mode - change directory
e  - command mode - edit file (edit/create a file)
j  - view mode - go one line down; to go a lot "down" use ctrl + D
k  - view mode - go one line up; to go a lot "up" use ctrl + U
u  - view mode - remove all made changes - after made changes in Insert Mode
<number> - command mode - view mode - go to line
/<pattern> - find by pattern - iterate by 'n' - next; 'f<symbol>' - find <symbol> in the line;
w - next word;
% - match bracket
c - change - flags: i - inside <bracket>;
d - delete - flags: i - inside <bracket>;
o - "open" new line under;
p - paste;

$ - end of line (same as regex)
^ - start of line (same as regex)


# Moving by words
press "w" then:
"b" - back
"e" - end of the word
"ge" - end of the word backwards

To **move extremely horizontally** use:

- **`0`**: Moves to the **first character of a line**
- **`^`**: Moves to the **first non-blank character of a line**
- **`$`**: Moves to the **end of a line**
- **`g_`**: Moves to the **non-blank character at the end of a line**

Starting from **`k`** and **`j`,** we move on to a **faster way of maneuvering vertically** with:

- **`}`** jumps entire paragraphs **downwards**
- **`{`** similarly but **upwards**
- **`CTRL-D`** lets you **move down half a page** by scrolling the page
- **`CTRL-U`** lets you **move up half a page** also by scrolling

# Search 

- Use **`/{pattern}`** to **search forward** inside a file
- Use **`?{pattern}`** to **search backwards**
	- n and N to next word up and down
	- "*" word under cursor
	- "#" - backwards

## Count command

{count}{command}

- **`2w`** allows us to move the cursor 2 words forward.
- **`5j`** changes your cursor position to 5 lines below.
- **`3;`** lets you go to the next third occurrence of a character.
- **`2/baby`** sends you flying to the second occurrence of `baby` in a document.


- Type **`gg`** to go to the top of the file.
- Use **`{line}gg`** to go to a specific line.
- Use **`G`** to go to the end of the file.
- Type **`%`** jump to matching **`({[]})`**.

## Operations

{operator}{count}{motion} 
{count}{operator}{motion}

- Use **`d5j`** to delete 5 lines downwards
- Type **`df'`** to delete everything in the current line from the cursor until the first occurrence of the **`'`** character (including the character itself)
- Or type **`dt'`** to do like the above example but excluding the character (so up until or just before the **`'`** character)
- Use **`d/hello`** to delete everything until the first occurrence of **`hello`**
- Type **`ggdG`** to delete a complete document


c - change
d - delete
y - yank (copy)
p - put  (paste)
g~ - (switch case) or use gU, and gu
\> - adds indentation
<   - remove indentation
= - format code

- **`c/hello`** changes everything until the first occurrence of `hello`.
- **`ggyG`** copies a whole document
- **`gUw`** capitalizes a word

   - **Capitalize an operator to have it perform a stronger (or alternate) version of its default behavior**: **`D`** deletes from the cursor to the end of the line, **`C`** changes to the end of a line, **`Y`** like **`yy`** copies a complete line, **`P`** pastes something before the cursor, etc.

{i|a}{text-object-id}
   i - inner
   a - around

## BuildIn text-objects are:
- **`w`** for **w**ord
- **`s`** for **s**entence
- **`'`**, **`"`**, **`` ` ``** for quotes
- **`p`** for **p**aragraph
- **`b`** (or **`(`**, **`)`**) for block surrounded by **`()`,**
- **`B`** (or **`{`**, **`}`**) for block surrounded by **`{}`**
- **`<`**, **`>`** for a block surrounded by **`<>`**
- **`[`**, **`]`** for a block surrounded by **`[]`**
- **`t`** for tag.

- **`daw`** to **d**elete **a** **w**ord (plus trailing whitespace)
- **`ciw`** to **c**hange **i**nner **w**ord
- **`das`** to **d**elete **a** **s**entence (**`dis`** to delete inner sentence)
- **`da"`** to delete something in double quotes including the quotes themselves (**`di"`** deletes only the content **i**nside the quotes and spares the quotes)
- **`ci"`** to change something inside double quotes
- **`dap`** to delete a paragraph
- **`dab`** **`da(`** or **`da)`** to delete a block surrounded by **`(`**
- **`daB`** **`da{`** or **`da}`** to delete a block surrounded by **`{`**
- **`dat`** to delete an HTML tag
- **`cit`** to change the contents of an HTML tag'


   - **`x`** is equivalent to **`dl`** and deletes the character under the cursor
- **`X`** is equivalent to **`dh`** and deletes the character before the cursor
- **`s`** is equivalent to **`ch`**, deletes the character under the cursor and puts you into _Insert mode_
- **`~`** to switch case for a single character
- "." - repeat last command
