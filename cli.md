## Using the Command Line

### Anatomy of a Command

I am fairly certain you have all extensively used computers in your life, whether that is a traditional desktop/laptop or just a smart phone. In general, these computers have programs with graphical interfaces. You start up a program, it presents you with an interface with various options and features that let you do a variety of things. These programs have **state**, you do something and the program remembers that, keeps that information in memory. We will largely be working with **command-line programs** which operate on a drastically different paradigm.

Instead of presenting you with an interface, options, and output all at once, or being able to do a variety of tasks while open, command-line programs generally do *one thing per execution*. This is both less convenient but potentially much more powerful, for reasons we will learn. To run a command-line program, you need one or more things:

- Mandatory: an executable program or command to run. Our example here will be `ls`, a command that lists files. By default, running `ls` lists the files in the current directory. You can find the manual for `ls` by running the command `man ls` or on a variety of websites: [https://man7.org/linux/man-pages/man1/ls.1.html](https://man7.org/linux/man-pages/man1/ls.1.html)
- *Arguments* - these are a set of "strings", basically textual words (though they need not be actual words!) that provide information to modify how the program runs. These can come in different *flavors*
- *Options* are a type of argument, usually beginning a dash, that modify how the command runs. These options are defined in the code of each program, and a list and explanation of each can be found in the manual. For `ls`, the parameter `-l` tells the command to provide a longer, more detailed, **l**ist format. This command invocation  might be called by running `ls -l`. These options can be **short**, starting with a single dash and consisting of a single letter, or **long**, two dashes followed by one or more words (without spaces).
- **Parameters** are another type of argument that provides *information* to the command. Unlike options, these strings can be many possible values. There are two types of parameters:
  - **Positional parameters** that provide information directly to the command. For `ls`, positional parameters tell the command which folder to list files for, instead of the current folder. The command `ls my_folder` lists the files in a folder called "my_folder", not the files in the current directory.
  - **Option parameters** provide information that modify an **option**. Some options have either optional or required parameters that can be provided. Our example, `ls`, for instance, has an option to color the filenames. This option is `--color`. This option optionally takes a parameter to specify when output should be colored, and can be "always", "auto", or "never". For `ls`, this option parameter is given by adding an equal symbol and then the parameter: `ls --color=always`. Not all programs work exactly the same way, for some, the parameter is given by putting a space between the option and the parameter. You can find out how to specify these parameters from instructions or the command manual.

These different arguments are often combined in a variety of ways. The flexibility provided by many options replaces extensive and complicated menu systems in graphical programs, while parameters take the place of things like file selection windows, tick boxes, or other methods of selection. We will be practicing using a variety of commands very soon.

### Common Notation

Both in our following training modules as well as other documentation and helpful sites on the internet, there are certain conventions regarding describing how commands work. We will use the ls manual page as an example here: [https://man7.org/linux/man-pages/man1/ls.1.html](https://man7.org/linux/man-pages/man1/ls.1.html) 

The synopsis of a command might look like this: 

```
ls [OPTION]... [FILE]...
```

This indicates a few things:
- The first element is the `ls`. This is the **command**.
- This is followed by `[OPTION]`. Frequently, square brackets indicate things that need to be replaced when you construct the command. You would substitute whichever options you wish to use for this.
- In this case, `[OPTION]` is followed by three periods `...` or an ellipsis. Ellipses are usually used to indicate that you can use more than one of the preceding element. This means that you can specify multiple options sequentially, for instance: `ls -l -a`
- Next is `[FILE]...` Similarly to before, this indicates you need to substitute in one or more arguments containing files at this position. In this case, these are the **positional parameters**. Earlier we said for `ls` these describe the files or folders that `ls` will list files for. It is in fact quite flexible and you can provide a whole list of folders, and it will list all of the files in each folder sequentially.
- The *order* of the elements in this description is frequently important. Many programs require that options be specified before the positional parameters.

I will re-emphasize that in most cases (I will try my best to be consistent in our training here) **square brackets indicate something you need to replace**. Square brackets have a advanced particular function in shell commands that we may or may not get to, you probably don't want them in your command for now!

###Documentation

In general, any command we use in this stream will have good documentation available somewhere. If these are built-in or common commands, which we will learn about in the next part of this module, you can get the manual inside of the shell by using the man or "manual" command followed by the command name (as a parameter!). You can also find (as I usually do) these manuals on the internet just by googling the name of the command followed by "manual". Although your RE and PRMs are available to help, I can recommend learning to read command "man pages" as well as web searching the command and finding often-helpful pages on [Stack Overflow](https://stackoverflow.com/).