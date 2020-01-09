# Git Configuration

## Usage

The most basic use case for git config is to invoke it with a configuration name, which will display the set value at that name. Configuration names are dot delimited strings composed of a 'section' and a 'key' based on their hierarchy. For example: user.email
```
git config user.email
```
In this example, email is a child property of the user configuration block. This will return the configured email address, if any, that Git will associate with locally created commits.

## Git Config Levels and Files

Before we further discuss git config usage, let's take a moment to cover configuration levels. The git config command can accept arguments to specify which configuration level to operate on. The following configuration levels are available:

- --local
  
By default, git config will write to a local level if no configuration option is passed. Local level configuration is applied to the context repository git config gets invoked in. Local configuration values are stored in a file that can be found in the repo's .git directory: .git/config
 
- --global
  
Global level configuration is user-specific, meaning it is applied to an operating system user. Global configuration values are stored in a file that is located in a user's home directory. ~ /.gitconfig on unix systems and C:\Users\<username>\.gitconfig on windows
 

- --system
  
System-level configuration is applied across an entire machine. This covers all users on an operating system and all repos. The system level configuration file lives in a gitconfig file off the system root path. $(prefix)/etc/gitconfig on unix systems. On windows this file can be found at C:\Documents and Settings\All Users\Application Data\Git\config on Windows XP, and in C:\ProgramData\Git\config on Windows Vista and newer.

Thus the order of priority for configuration levels is: local, global, system. This means when looking for a configuration value, Git will start at the local level and bubble up to the system level.

## Writing a Value

Expanding on what we already know about git config, let's look at an example in which we write a value:
```
git config --global user.email "your_email@example.com"
```
This example writes the value your_email@example.com to the configuration name user.email. It uses the --global flag so this value is set for the current operating system user.

## Git Config Editor - core.editor

Many Git commands will launch a text editor to prompt for further input. One of the most common use cases for git config is configuring which editor Git should use. Listed below is a table of popular editors and matching git config commands:

|       Editor       |                                 Config Command                                  |
| :----------------: | :-----------------------------------------------------------------------------: |
|        Atom        |                ~ git config --global core.editor "atom --wait"~                 |
|       emacs        |                   ~ git config --global core.editor "emacs"~                    |
|        nano        |                  ~ git config --global core.editor "nano -w"~                   |
|        vim         |                    ~ git config --global core.editor "vim"~                     |
| Sublime Text (Mac) |                 ~ git config --global core.editor "subl -n -w"~                 |
|    Sublime Text    | ~ git config --global core.editor "'c:/program files/sublime text 3/sublimetext |
|      Textmate      |                  ~ git config --global core.editor "mate -w"~                   |

## Merge Tools

In the event of a merge conflict, Git will launch a "merge tool." By default, Git uses an internal implementation of the common Unix diff program. The internal Git diff is a minimal merge conflict viewer. There are many external third party merge conflict resolutions that can be used instead. For an overview of various merge tools and configuration, see our guide on tips and tools to resolve conflits with Git.
```
git config --global merge.tool kdiff3
```

## Aliases

You may be familiar with the concept of aliases from your operating system command-line; if not, they're custom shortcuts that define which command will expand to longer or combined commands. Aliases save you the time and energy cost of typing frequently used commands. Git provides its own alias system. A common use case for Git aliases is shortening the commit command. Git aliases are stored in Git configuration files. This means you can use the git config command to configure aliases.

```
git config --global alias.ci commit
```
This example creates a ci alias for the git commit command. You can then invoke git commit by executing git ci. Aliases can also reference other aliases to create powerful combos.
```
git config --global alias.amend ci --amend
```
This example creates an alias amend which composes the ci alias into a new alias that uses --amend flag.

## Formating & Whitespaces

Git has several "whitespace" features that can be configured to highlight whitespace issues when using git diff. The whitespace issues will be highlighted using the configured color color.diff.whitespace

The following features are enabled by default:

- blank-at-eol highlights orphan whitespaces at the line endings
- space-before-tab highlights a space character that appears before a tab character when indenting a line
- blank-at-eof highlights blank lines inserted at the end of a file

The following features are disabled by default

- indent-with-non-tab highlights a line that is indented with spaces instead of tabs
- tab-in-indent highlights an initial tab indent as an error
- trailing-space is shorthand for both blank-at-eol and blank-at-eof
- cr-at-eol highlights a carriage-return at the line endings
- tabwidth=<n> defines how many character positions a tab occupies. The default value is 8. Allowed values are 1-63

## Summary

In this article, we covered the use of the git config command. We discussed how the command is a convince method for editing raw git config files on the filesystem. We looked at basic read and write operations for configuration options. We took a look at common config patterns:

- How to configure the Git editor
- How to override configuration levels
- How to reset configuration defaults
- How to customize git colors
  
Overall, git config is a helper tool that provides a shortcut to editing raw git config files on disk. We covered in depth personal customization options. Basic knowledge of git configuration options is a prerequisite for setting up a repository. See our guide there for a demonstration of the basics.