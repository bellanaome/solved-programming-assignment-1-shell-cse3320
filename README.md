Download Link: https://assignmentchef.com/product/solved-programming-assignment-1-shell-cse3320
<br>
<h1>Description</h1>

In this assignment you will write your own shell program, Mav shell (msh), similar to bourne shell (bash), c-shell (csh), or korn shell (ksh). It will accept commands, fork a child process and execute those commands. The shell, like csh or bash, will run and accept commands until the user exits the shell. Your file must be named msh.c

<h1>Functional Requirements</h1>

<strong>Requirement 1</strong>: Your program will print out a prompt of msh&gt; when it is ready to accept input. It must read a line of input and, if the command given is a supported shell command, it shall execute the command and display the output of the command.

<strong>Requirement 2</strong>: If the command is not supported your shell shall print the invalid command followed by “: Command not found.”

<strong>Requirement 3</strong>: If the command option is an invalid option then your shell shall print the command followed by “: invalid option –” and the option that was invalid as well as a prompt to try —help. <strong>exec() output this automatically make sure you pass it on to your user.  </strong>

<strong>Requirement 4</strong>: After each command completes, your program shall print the msh&gt; prompt and accept another line of input.

<strong>Requirement 5</strong>: Your shell will exit with status zero if the command is “quit” or “exit”.

<strong>Requirement 6</strong>: If the user types a blank line, your shell will, quietly and with no other output, print another prompt and accept a new line of input.

<strong>Requirement 7</strong>: Your shell shall support suspending the process with ctrl-z

<strong>Requirement 8</strong>: Your shell shall background a suspended process with bg

<strong>Requirement 9</strong>: Your version of Mav shell shall support up to 10 command line parameters in addition to the command.

<strong>Requirement 10</strong>: Your shell shall support and execute any command entered. Any

command in /bin, /usr/bin/, /usr/local/bin/ and the current working directory is to be considered valid for testing.

Your shell shall search in the following PATH order:

<ol>

 <li>Current working directory,</li>

 <li>/usr/local/bin</li>

 <li>/usr/bin</li>

 <li></li>

</ol>

<table>

 <tbody>

  <tr>

   <td width="156"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<ul>

 <li>/bin</li>

</ul>

Parameters may also be combined. For example, ps may be executed as: ps –aef or ps –a –e -f

<strong>Requirement 11:</strong> Mav shell shall be implemented using fork(), wait() and one of the exec family of functions.

Your Mav shell shall not use system(). Use of system() will result in a grade of 0.

<strong>Requirement 12</strong>: Typing ctrl-c or ctrl-z shall not stop or kill your shell. ctrl-z shall suspend the currently running process. ctrl-c shall stop the currently running process.

<strong>Requirement 13</strong>: Your shell shall support the cd command to change directories. Your shell must handle cd ..

<strong>Requirement 14</strong>: Your shell shall support the listpids command to list the PIDs of the last 15 processes spawned by your shell. If there have been less than 15 processes spawned then it shall print only those process PIDs

<strong>Requirement 15</strong>: Your shell shall support the history command which will list the last 15 commands entered by the user. Typing !n, where n is a number between 1 and 15 will result in your shell re-running the nth command.  If the nth command does not exist then your shell will state “Command not in history.”.  The output shall be a list of numbers 1 through n and their commands, each on a separate line, single spaced.

<strong>Requirement 16</strong>: Your source file shall be named msh.c.  The source files must be ASCII text files. No binary submissions will be accepted.

<strong>Requirement 17</strong>: Tabs or spaces shall be used to indent the code. Your code must use one or the other. All indentation must be consistent.

<strong>Requirement 18</strong>: No line of code shall exceed 100 characters.

<strong>Requirement 19</strong>: Each source code file shall have the following header filled out:

<strong>Requirement 20</strong>: All code must be well commented. This means descriptive comments that tell the intent of the code, not just what the code is executing.

The following are poor comments.

The following explains the intent:

When in doubt over comment your code.

<strong>Requirement 21</strong>: Keep your curly brace placement consistent. If you place curly braces on a new line , always place curly braces on a new end. Don’t mix end line brace placement with new line brace placement.

<strong>Requirement 22</strong>: Each function should have a header that describes its name, any parameters expected, any return values, as well as a description of what the function does.

For example

<strong>Requirement 23</strong>: Remove all extraneous debug output before submission. The only output shall be the output of the commands entered or the shell prompt.

<strong>Requirement 24</strong>: Your code shall compile cleanly on <a href="http://omega.uta.edu/">omega.uta.edu</a> with no warnings using: gcc -Wall msh.c -o msh <strong>Administrative</strong>

This assignment must be coded in C. Any other language will result in 0 points. You programs will be compiled and graded on omega.uta.edu. Please make sure they compile and run on omega before submitting them.  Code that does not compile on omega with:

gcc -Wall msh.c -o msh will result in a 0.

Your program, msh.c is to be turned in via blackboard. Submission time is determined by the blackboard system time. You may submit your programs as often as you wish. Only your last submission will be graded.

There are coding resources and working code you may use on Blackboard and in the course github repository at: https://github.com/CSE3320/Shell-Assignment . You are free to use any of that code in your program if needed.  You may use no other outside code.

<h1>Hints</h1>

Read the man pages for the following: fork, exec, exit, print, fgets, strtok, strsep, strcmp, wait, and pause.

Use fork and one of the exec family as discussed in class to execute the command and call wait to wait for the child to complete. If the command is “cd” then use chdir() instead of exec. Note, chdir() must be called from the parent.

If you see garbage in any of your commands or parameters, try using the functions memset() or bzero() to clear out your input string and token array before and/or after you are done using them. Also, verify you are NULL terminating your strings.

https://stackoverflow.com/questions/12683466/after-suspending-child-process-with-sigtstpshell-not-responding