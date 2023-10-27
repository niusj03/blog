---
title: 'Linux and Command Line'
date: 2022-10-11T20:11:33+08:00
draft: false
tags: ["html", "css"]
categories: ["tech"]
---

# Brief Introduction to Shell

**Shell**:
A shell is an environment in which various commands can be executed, it provides an interface between the user and the UNIX system. Basically, a shell is a command-line interpreter which is interprets the commands given by the user, it can also read the combination of such commands which is known as a shell script. The shell provides us with an environment in which we can execute our commands, scripts, and programs.

There are two most popular shells **bash** and **zsh**. The detailed compare of difference is [here](https://www.geeksforgeeks.org/bash-scripting-difference-between-zsh-and-bash/). Here is the basic introduction of these two shells.

**Bash (Bourne Again SHell)**:
Bash is a popular command-line shell and scripting language. It is an enhanced version of the original Bourne shell (`sh`). Introduced in 1989, Bash became the default shell for the Linux operating system and macOS (up until macOS Catalina, after which it switched to `zsh` as the default). Bash scripts usually have a `.sh` extension, though it's not a strict requirement.

Features of Bash:
1. **Command-line editing**: Allows users to move the cursor, search command history, etc.
2. **Job control**: You can put jobs (commands) in the background and bring them to the foreground.
3. **Command history**: Stores a list of commands you have previously executed.
4. **Scripting capabilities**: You can automate tasks by writing Bash scripts.
5. **Filename wildcarding**: Allows you to use patterns to match filenames (e.g., `*.txt`).
6. **Array variables**: Supports one-dimensional arrays.
7. **Command substitution**: Allows the output of a command to replace the command itself.
8. **And more**: Including functions, variables, control structures, etc.

**Zsh (Z Shell)**:
Zsh is another command-line shell that's designed to be interactive and is often considered an extended Bourne shell with many improvements, including those of Bash, `ksh`, and `tcsh`.

Features of Zsh:
1. **Interactive command-line editing**: Like Bash but with extended functionalities.
2. **Shared command history**: Commands entered in one terminal can be seen in the command history of another.
3. **Extended file globbing**: Offers more advanced pattern-matching features than Bash.
4. **Improved variable/array handling**: Such as associative arrays.
5. **Spelling correction**: If you type a command or filename incorrectly, Zsh can suggest corrections.
6. **Loadable modules**: Allows the shell to be extended with additional functions.
7. **Themeable prompts**: Including the popular Powerlevel9k and Powerlevel10k themes.
8. **Plugin and theme system**: Tools like Oh-My-Zsh provide a wealth of plugins, themes, and features to customize the Zsh experience.

Choosing between Bash and Zsh often comes down to personal preference. While Bash is more widespread due to its presence on many systems by default, Zsh has gained popularity due to its extensive features and customization capabilities, especially with the adoption of tools like Oh-My-Zsh. If you're new to the command line, starting with Bash makes sense, as it's more commonly available and its skills are highly transferable. If you're looking for a richer, more customizable experience, then exploring Zsh might be the way to go.


### .bashrc / .zshrc


These are configuration files that are executed whenever an instance of a shell (zsh or bash) is started. These files allow users to customize their shell environment.

1. **`.bashrc`**:
   - This is a shell script that Bash runs whenever it's started interactively.
   - It initializes an interactive shell session. Users can put any command in this file to run when a Bash shell is opened. Common uses include setting environment variables, defining shell functions, and setting aliases.
   
2. **`.zshrc`**:
   - Similar to `.bashrc` but for the Zsh shell.
   - This is where users can put commands that run whenever an interactive Zsh session is started. It's commonly used to define shell customizations specific to Zsh.


when you have downloaded and installed Miniconda in your server and then you need to initialize the `Conda` environment system for your shell sessions. The detailed explanation is as follow:

<details> 
<summary>Explanation for Initializtion of Conda</summary>

After installing, initialize your newly-installed Miniconda. The following commands initialize for bash and zsh shells:
```bash
~/miniconda3/bin/conda init bash
~/miniconda3/bin/conda init zsh
```
And the .bashrc and .zsh will add following code snippet.
```bash
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/23040942r/miniconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/xxxxxxxxr/miniconda3/etc/profile.d/conda.sh" ]; then
        . "/home/xxxxxxxxr/miniconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/xxxxxxxxr/miniconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```
The code snippet you provided is added to the .bashrc file by the Conda initializer to set up the Conda environment for the shell.

**About PATH:**
The PATH variable is an environment variable on Unix-like operating systems, DOS, OS/2, and Microsoft Windows, specifying a set of directories where executable programs are located.

In general:

When you type a command in the terminal, the system looks for that command in the directories specified by the PATH variable.
Directories in the PATH are separated by a colon, `:` in Unix-like systems.
The system searches the directories in the order they are listed in PATH.
</details>


During Miniconda (or Anaconda) installation

    1. The installer might ask if you want to prepend the Miniconda install location to your `PATH`. If you agree:
    - For **Bash**, it will modify either `.bashrc` or `.bash_profile`.
    - For **Zsh**, it will modify `.zshrc`.

    2. Once these modifications are made, any new shell session you start will have Conda initialized, meaning the `conda` command will be available, and the base Conda environment will be activated by default.

    3. If you choose not to let the installer modify your shell's rc file, you can always manually add the necessary lines to initialize Conda in your shell sessions.

    Remember, after making changes to `.bashrc` or `.zshrc`, you'll typically want to either start a new shell session or source the file (using a command like `source ~/.bashrc` or `source ~/.zshrc`) to apply the changes to your current session.


# 