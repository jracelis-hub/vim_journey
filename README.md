# Vim Knowledge

## ***Table of Contents***

* [***Introduction***](#introduction)
	* [_Terminal Manipulation_](#terminal-manipulation)
* [***How To: Normal Mode***](#how-to:-normal-mode)
	* [_Navigate Through Vim_](#how-to-navigate-through-vim)
	* [_Setup Config_](#how-to-setup-config)
* [***Cheatsheets***](#cheatsheets)

## ***Introduction***

***What is VIM***

Vim or (Vi IMproved) is a power text editor which is an improved version of Vi (Visual Editor).

* When you use `:` that is calling a command within ***vim***.
* When you used `:!` then you are calling a command within the terminal.

Example
```
vim file.txt
:!ls
# This will list the files within current directory as if you did it on the command line
```

### ***Terminal Manipulation

* To open up a terminal while in vim do
	* `:ter` This will open up a terminal in a screen above.
* To split screen up vertically
	* `vsplit`
	* shortcut `vsp`
* To split screen up horizontally
	* `split`
	* shortcut `sp`


## ***HOW To: Normal Mode***

### ***How to Navigate Through VIM***

* To jump to a specific line use `:n` where n is the line number shown on the left.
* To jump to the end of the page `G`
* To jump to the beginning of the page `gg`
* To jump to beginning of the line `0`
* To jump to end of the line `$`
* To jump to beginning of word going right `w`
* To jump to beginning of word going back `b`

> [!TIP] 
> You can use the navigation keys `w` `b` `e` with other commands like `d` (deletion) `c` cutting

### ***How to Delete, Copy, Paste and Cut***

<table style>
	<thead>
		<tr>
			<th align="center" colspan="2">Delete</th>	
			<th align="center" colspan="2">Copy (Yank)</th>	
			<th align="center" colspan="2">Paste</th>	
			<th align="center" colspan="2">Cut</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td align="center" >Command</td>
			<td align="center" >Description</td>
			<td align="center" >Command</td>
			<td align="center" >Description</td>
			<td align="center" >Command</td>
			<td align="center" >Description</td>
			<td align="center" >Command</td>
			<td align="center" >Description</td>
		</tr>
		<tr>
			<td align="center" >`dd`</td>
			<td>to delete a line</td>
			<td align="center" >`yy`</td>
			<td>to copy a line</td>
			<td align="center" >`p`</td>
			<td>to paste below a line or after the cursor</td>
			<td align="center" >`cc`</td>
			<td>to delete a line and go into insert mode</td>
		</tr>
		<tr>
			<td align="center" >`ndd`</td>
			<td>to delete n lines</td>
			<td align="center" >`nyy`</td>
			<td>to copy n lines</td>
			<td align="center" >`np`</td>
			<td>to paste the same item n times</td>
			<td align="center" >`ncc`</td>
			<td>to delete n lines and go into insert mode</td>
		</tr>
		<tr>
			<td align="center" >`ndd`</td>
			<td>to delete n lines</td>
			<td align="center" >`nyy`</td>
			<td>to copy n lines</td>
			<td align="center" >`np`</td>
			<td>to paste the same item n times</td>
			<td align="center" >`cc`</td>
			<td>to delete n lines and go into insert mode</td>
		</tr>
	</tbody>
</table>

_Delete_

`dd` to delete a line

`ndd` to delete _n_ below lines

`dw` to delete one word after the cursor

`dnw` to delete n words after the cursor

`di$` to delete in `c`haracter 

> [!WARNING]
> If the cursor is not at the beginning of the word it will only delete from the letter of the cursor

`d$` to delete from start of the cursor to end of the line

`d0` to delete from one space back from the cursor to the beginning of the line

`d%` to delete to the to the end of the first occurence of `)` `}` or `]`

_Copy (Yank)_

`yy` to copy a line

`nyy` to copy n lines below

`yw` to copy a word from cursor to end of a word

`ynw` to copy n words from cursor

`y$` to copy every after the cursor to end of the line

`y0` to copy from one space back from cursor to the beginning of the line

_Paste_

`p` to paste after cursor but if you use `dd` then `p` it will paste below the line

`P` to paste before cursor but if you use `dd` then `P` it will paste above the line

`np` to paste the same items n times

_Cut + (into Insert mode)_

`cc` to cut a line and go into `insert` mode

`cw` to cut a word and go into `insert` mode

`cic` to cut `i`n a `c`haracter and go into `insert` mode

`C` to cut a line and go into `insert` mode

### ***How to Setup Config***

In your `$HOME` or `~` directory make a file called `vimrc`

```bash
cd $HOME
vim vimrc
```

Specific Configuration Table

|Purpose| Description|
|:---:|:------|
| `set number` | to add line numbers on your vim console |
| `set relativenumber` | to show relative line numbers |
| `set autoindent` | to place the same indentations on the new line, as is present on the previous line |
| `set shiftwidt=number` | indent size of shift width |
| `set tabstop=number` | tab size |
| `set mouse=a` | allows mouse movements |

| Cursor Change | Description |
|:---:|:---| 
| Ps = 0 | blinking block |
| Ps = 1 | blinking block |
| Ps = 2 | steady block |
| Ps = 3 | blinking underline |
| Ps = 4 | steady underline |
| Ps = 5 | blinking bar |
| Ps = 6 | steady bar |
| `let &t_EI` | "\e[2 q" " Set all settings to blinking block |
| `let &t_SI` | "\e[5 q" " Set insert mode to have steady bar |
| `let &t_SR` | "\e[3 q" " Set replace mode to have steady underline |

> [!NOTE]
> To add comments use `"` before the new line 

## ***Cheatsheets***

Good to know hotkeys for Vim

| Insert Mode | Description |
|:---:|:---------------|
| `i` | to go into insert mode at the location of your cursor |
| `I` | insert at the begginng of the line |
| `a` | insert (append) after the cursor |
| `A` | insert (append) at the end of the line |
| `o` | append (open) a new line below the current line |
| `O` | append (open) a new line above the current line |
| `crtl` + `h` | delete character before the cursor during insert mode |
| `crtl` + `w` | delete word before the cursor during insert mode |
| `crtl` + `j` | add a line break at the cursor position during insert mode |
| `crtl` + `t` | indent (move right) line on shiftwidth during insert mode |
| `crtl` + `d` | de-indent (move left) line one shiftwidth during insert mode |
| `esc` or `crtl` + `c` | exit insert mode |

| Cursor Movement | Description |
| :---: |:---------------------|
| `h` | move cursor left |
| `j` | move cursor down |
| `k` | move cursor up |
| `l` | move cursor right |
| `nj` | moves cursor down (multi-line text)
| `nk` | moves cursor up (multi-line text)
| `H` | move to top of screen |
| `M` | move to middle of screen |
| `L` | move to bottom screen |
| `gg` | go to the first line of the document |
| `G` | go to the last line of the document |
| `w` | jump forwards to the start of a word |
| `W` | jumps forwards to the start of a word (words can contain punctuation) |
| `e` | jumps forwards to the end of a word |
| `E` | jumps fowards to the end of a word (words can contain punctuation |
| `b` | jumps backwards to the start of a word |
| `B` | jump backwards to the start of a word (words can contain punctuation) |
| `0` | jump to the start of the line |
| `$` | jump to end of the line |
