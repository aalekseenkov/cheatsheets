# Command Line Editing

The bash shell includes a library called readline to handle keyboard input during interactive shell sessions. This includes text typed at the shell prompt and keyboard input using the read builtin when the -e option is specified. The readline library supports a large number of commands that can be used to edit what we type at the command line. Since readline is from the GNU project, many of the commands are taken from the emacs text editor.

## Control Commands 

Here are some commands to control the editing process.

| Command | Description                      |
|---------|----------------------------------|
| Enter   | Pressing the enter key causes the current command line to be accepted. Note that the cursor location within the line does not matter (i.e., it doesn’t have to be at the end). If the line is not empty, it is added to the command history. |
| Esc     | Meta-prefix. If the Alt key is unavailable, the Esc key can be used in its place. For example, if a command calls for Alt-r but another program intercepts that command, press and release the Esc key followed by the r key. |
| Ctrl-g  | Abort the current editing command. |
| Ctrl-_  | Incrementally undo changes to the line. |
| Alt-r   | Revert all changes to the line (i.e., complete undo). |
| Ctrl-l  | Clear the screen. |
| Alt-num | Where num is a number. Some commands accept a numeric argument. For those commands that accept it, type this first followed by the command. |

_Editing control commands_

## Moving Around

Here are some commands to move the cursor around the current command line. In the 
readline documentation, the current cursor location is referred to as the point.

| Command | Description                       |
|---------|-----------------------------------|
| Ctrl-f  | Right Move forward one character. |
| Ctrl-b  | Left Move backward one character. |
| Alt-f   | Move forward one word.            |
| Alt-b   | Move backward one word.           |
| Ctrl-a  | Move forward one character.       |
| Ctrl-e  | Move to the end of the line.      |

_Cursor movement commands_

## Using Command History

In order to save typing, we frequently reuse previously typed commands stored in the command history. We can move up and down the history list and the history list can be searched.

| Command    | Description |
|------------|-------------|
| Ctrl-p     | Move to previous history list entry. |
| Ctrl-n     | Move to next history list entry. |
| Alt-<      | Move to the beginning of the history list. |
| Alt->      | Move to the end of the history list. |
| Ctrl-r     | Perform an incremental history search starting at the current position and moving up the history list. After a command is typed, a prompt appears and with each succeeding character typed, the position within the list moves to the next matching line. This is probably the most useful of the history search commands. |
| Ctrl-s     | Like Ctrl-r except the search is performed moving down the history list. |
| Alt-p      | Perform a non-incremental search moving up the history list. |
| Alt-n      | Perform a non-incremental search moving down the history list. |
| Alt-Ctrl-y | Insert the first argument from the previous history entry. This command can take a numeric argument. When a numeric argument is given, the nth argument from the previous history entry is inserted. |
| Alt-.      | Insert the last argument from the previous history entry. When a numeric argument is given, behavior is the same as Alt-Ctrl-y above. |

_History commands_

## Changing Text

| Command | Description |
|---------|-------------|
| Ctrl-d  | Delete the character at the point.     |
| Ctrl-t  | Transpose characters. Exchange the character at the point with the character preceding it. |
| Alt-t   | Transpose words. Exchange the word at the point with the word preceding it. |
| Alt-u   | Change the current word to uppercase. |
| Alt-l   | Change the current word to lowercase. |
| Alt-c   | Capitalize the current word. |

_Editing commands_

## Cutting and Pasting

As with vim, cutting and pasting in readline are referred to as “killing” and “yanking.” The clipboard is called the kill-ring and is implemented as a circular buffer. This means that it contains multiple entries (i.e., each kill adds a new entry). The latest entry is referred to as the “top” entry. It is possible to “rotate” the kill-ring to bring the previous entry to the top and delete the latest entry. However, this feature is rarely used. Mostly, the kill commands are used to simply delete text rather than save it for later yanking.

| Command       | Description |
|---------------|-------------|
| Alt-d         | Kill from the point to the end of the current word. If the point is located in whitespace, kill to the end of the next word. |
| Alt-Backspace | Kill the word before the point. |
| Ctrl-k        | Kill from the point to end of line. |
| Ctrl-u        | Kill from the point to the beginning of the line. |
| Ctrl-y        | Yank the “top” entry from the kill-ring. |
| Alt-y         | Rotate the kill-ring and yank the new “top” entry. |

_Copy and delete commands_

## Notes
* The READLINE section of the bash man page describes the many keyboard shortcuts available on the command line.
* Command Line Editing are discussed in Chapter 3 of _Adventures with the Linux Command Line_: https://linuxcommand.org/lc3_adventures.php
