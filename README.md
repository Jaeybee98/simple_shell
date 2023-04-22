## Simple Shell > In this project, we coded from scratch a simple Unix shell. A shell is an interactive > command-line interpreter. We created a shell that would utilize the command line > interface (CLI). It allows users to type in a defined set of > commands (e.g. "rm" to remove files, "cat" to combine word documents, etc) and have the > operating system run the appropriate function. It is slightly different from a graphical user > interface (GUI). For instance, instead of using a mouse to click to open folders and delete files, a user > can type in a command (i.e. "ls" or "rm") and have the files be displayed or > modified in a list on the command line. GUI and CLI both have the same purpose to interact > with the operating system but their input methods are different and some developers > prefer the CLI to interact with the shell because their typing is quicker than > clicking and dragging. There are a few > versions of Unix shells, from the very first (Ken Thompson's) shell that can > be activated by typing ```sh``` in the terminal to today's most popular Bash > (Bourne Again Shell). Later versions of the shell handle memory leaks better and > have more functionality. Our shell is a simple version that handles memory leaks > very well and has basic functionality. You can create/write/read/open/remove > folders, print things to the terminal, change directories, print where you are > in the system, etc.

Synopsis
This repository holds all the code necessary for our custom simple shell to run. Our shell currently handles the executions of executables found in the environmental variable PATH, with or without their full paths. Sample commands that our shell supports include ls (/bin/ls), pwd, echo, which, whereis, etc. We've also created the following builtins.

Builtins
exit exits shell (Usage: exit [status])
env prints environmental variables (Usage: env)
setenv creates or modifies an environmental variable (Usage: setenv name value)
unsetenv removes an envrionmental variable (Usage: unsetenv name value)
cd changes directories (Usage: cd [-][~][path])
Functions and system calls used
read, signal, malloc, free, getcwd, chdir, access, execve, wait, write, exit

Description of what each file shows:
man_3_shell ------------------------ custom manpage for our simple shell
main.c ----------------------------- holds entrance into program
shell.h ---------------------------- holds prototypes of functions spread across all files
Helper files

prompt.c --------------------------- handles outline of shell's reprompting and executing
non_interactive.c ------------------ handles output when shell is called outside of shell
_realloc.c ------------------------- helper function handles reallocation
_strcat.c -------------------------- concatenates two strings
_strcmp.c -------------------------- compares if two strings match
_strcpy.c -------------------------- copies a string
_strdup.c -------------------------- duplicates a string
_str_tok.c -------------------------- (custom) tokenizes user's command input and returns array
c_str_tok.c ------------------------- tokenizes PATH to include ":" as Null, checks current dir
get_line.c ------------------------- (custom) reads user's typed input into buffer
_which.c --------------------------- appends command to PATHs, fleshes paths out, returns match
_cd.c ------------------------------ changes directories
linked_lists.c --------------------- adds and deletes nodes; prints and frees linked list
get_env.c -------------------------- finds and returns copy of environmental variable
env_linked_list.c ------------------ prints and creates linked list of envrionmental variables
set_unset_env.c -------------------- finds environment variable index node, sets and unsets
free_double_ptr -------------------- frees double pointers (user's command, arrays)
_execve.c -------------------------- executes and frees command, then exits program
__exit.c --------------------------- handles if user types exit or exit(value)
int_to_string.c -------------------- converts int to string to write error messages
print_error.c ---------------------- prints special error messages for certain fails 
