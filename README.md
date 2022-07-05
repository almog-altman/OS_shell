# OS_shell
Operating systems

In this mini-project I implemented a multiprocess Unix Shell program in C.

The implementation includes important multiprocessing concepts such as signal handling,
pipes for multiprocess communication, handling zombies, working with files and the standard input/output.

The shell supports the following operations:
1. Executing commands. The user enters a command, i.e., a program and its arguments, such as sleep 10.
The shell executes the command and waits until it completes before accepting another command.
2. Executing commands in the background. The user enters a command followed by &,
for example: sleep 10 &. The shell executes the command but does not wait for its completion
before accepting another command. (It is also dealing with zombies)
3. Single piping. The user enters two commands separated by a pipe symbol (|), for example:
cat foo.txt | grep bar. The shell executes both commands concurrently, piping the standard
output of the first command to the standard input of the second command. The shell waits until
both commands complete before accepting another command.
4. Output redirecting. The user enters one command and an output file name separated by the
redirection symbol (>>), for example: cat foo >> file.txt. The shell executes the command
so that its standard output is redirected to the output file (instead of the default, which is to the
user’s terminal). If the specified output file does not exist, it is created. If it exists, it is appended.
The shell waits for the command completion before accepting other commands.

*The shell doesn’t support built-in commands such as cd and exit.
*The part that I implemented is myshell.c

Run this to compile:
gcc -O3 -D_POSIX_C_SOURCE=200809 -Wall -std=c11 shell.c myshell.c
