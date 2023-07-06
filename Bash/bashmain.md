# Bash Notes

Every Windows PC comes with Command Prompt (cmd), a command-line textual interface to your operating system. Using Command Prompt, you can install programs, run scripts, and much more. The closest equivalent to cmd for Unix-like machines is Bash. Bash is often seen as superior because of its powerful features including arithmetic, array variables, loops, and branches. Git is fundamentally a Unix-style command-line utility program. It even comes installed on some macOS and Linux systems. Git Bash provides Windows users with access to Bash and its advanced features.

Bash is an acronym - Bourne Again Shell. The name is a pun on the Bourne shell which it replaced. Bash has all the Bourne shell core features such as grammar and variable expansion. What makes it “born again” are several additional features, including:

- Multi-character invocation options
- Command-line editing
- Timestamped command-line history
- One-dimensional built-in array variables
- For loop expressions
- Job control
- Aliases

Git Bash is strictly for Windows users. It provides an emulation of both Git and the Bash command-line environment. Installing Git Bash on your Windows machine gives you access to a shell environment that is native to macOS and Linux users.

## [Sources and Further Reading](#sources)

## [Back to main](../main.md)

---

### Common Git Bash Commands

Note that the Bash commands that you can use are case-sensitive. This is in contrast with the cmd, many parts of which are case-insensitive.

### Change directory

> cd

Lets you navigate from one directory to another. All you need to provide is the path to the destination directory:

```bash
cd directory_path
```

If you do not provide a directory path after the cd command, it will take you to your home directory. You can also navigate to the parent directory of the one you’re currently in:

```bash
cd ..
```

### Create directory

> mkdir

Allows you to create a new directory. All you need to provide is the desired directory name:

```bash
mkdir directory_name
```

The above code will create a new subdirectory of the directory you are currently in.

### Remove directory

> rmdir

Removes empty directories. `rmdir` can delete one or more directories at a time, the only requirement is that they should be empty. If you want to delete many separate empty directories, the order is important. Make sure you delete child directories before any of their parents, or the parent directories will not be empty when rmdir tries to remove them:

```bash
rmdir main_directory/sub_directory main_directory
```

### Delete File

> rm

Delete specific files from directories. Requires the path to the file you want to delete:

```bash
rm directory_path/file
```

It also allows you to delete populated (Not empty) directories using specific options. To do so, use one of the following options:

- -r
- -R
- --recursive

All these options are equivalent and they will delete files recursively. This means that `rm` will delete any given directories, and all the files underneath them, including any subdirectories.

### Move File

> mv

Allows you to move a file or folder to any directory. Takes two arguments. a file name and a directory path.

```bash
mv file.extension directory_path
```

You can also use mv to rename a file since that operation is a special case of moving it:

```bash
mv file1.txt file2.txt
```

### List Files

> ls

ls (LS) lists all the files and folders in a directory

```bash
ls directory_name
```

### Echo

> echo

Prints a string to the Git Bash terminal

```bash
echo "string"
```

### Concatenate

> cat

This command has several options and three main functions.

- Create and append to a file

```bash
cat >file.extension
```

After executing this command, Git Bash will remain in the newly created file and allow you to append to it. If you want to exit, press `Ctrl+C`.

- View the contents of a file

```bash
cat file.extension
```

You should always include the extension of the file you want to read from, or else Git Bash will not locate the file.

- Append one file to the end of another

```bash
cat file.extension >> file2.extension
```

In this example, Git Bash appends the content of file1.txt to the end of file2.txt. If you forget the extension for the first file, Git Bash will not locate it. If you forget the extension for the second file, Git Bash will create a new file.

---

## Sources

[Simple Bash Guide](https://www.makeuseof.com/git-bash-what-how-use/)

[Git Documentation](https://git-scm.com/)
