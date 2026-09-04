What I Learned:
This video introduced the basics of Vim, a terminal-based text editor used to create and edit files directly from the Linux command line.
I learned that Vim works with different modes, and understanding these modes is important because the same key can perform different actions depending on the current mode.

Vim Modes
The main modes I learned about were:
•	Normal mode — Used for navigating through a file and performing editing actions.
•	Insert mode — Used for actually typing and inserting text into the file.
•	Command mode — Used to enter commands for actions such as saving or exiting Vim.

I learned that when Vim opens, it starts in Normal mode. To start typing text, I can press:
i
This changes Vim from Normal mode to Insert mode.

After editing the text, I can press:
Esc
to return to Normal mode.

From Normal mode, I can then use : to enter Command mode. This allows me to perform commands such as saving and exiting the editor.
For example:
:w
saves the file, while:
:q
quits Vim.
I can also combine them:
:wq
to save the file and exit.

Basic Copying and Pasting
I was also introduced to Vim's basic copying and pasting commands.
In Normal mode:
yy
copies the current line.
The copied line can then be pasted using:
p
This allows me to quickly duplicate lines without having to retype them.

Practising with Vim
I also spent some time using:
vimtutor
The Vim tutor provides an interactive way to practise Vim commands directly in the terminal. Using it myself helped me get more comfortable with navigating, switching modes, editing text, and using basic Vim commands.

Overall Understanding
This lesson introduced me to the basic workflow of editing files with Vim. The most important concept for me was understanding the difference between Normal mode, Insert mode, and Command mode, and knowing how to move between them.
I only covered the fundamentals in this lesson, including inserting text, navigating, copying and pasting, saving, and exiting Vim. I also used vimtutor to practise these commands and get some hands-on experience with the editor.

