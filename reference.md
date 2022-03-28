# Command reference for Linux 

## Becoming a Linux Power User

---

### Help!

Being able to help yourself is a loyal companion! It comes in the form of the
*Information quadrega* for the *general user*:

| Syntax | Description |
| ------ | ----------- |
|`type <command>`| Show me location & type of `<command>` |
|`info <command>`| Show me the info document of `<command>` |
|`man <command>`| Show me the command manual of `<command>` |
|`man -k <command>`| Search the name & summary section of all manpages for `<command>` |
| `<command> --help` | Show me the reference manual of `<command>` |

**Useful Examples**

| `man <command> | less` | Page through a manual side by side (..usefull with large files)
| `<Space>` | Move by page |
| `<Enter>` | Move by page |

*Note*: if `man -k` does not give output, initialize the man page data base:

| `mandb` | Initialize the man page database |

*Information quadrega* for the *system administrator*:

| Syntax | Description |
| ------ | ----------- |
|`man 1 <command>`| Show me the user commands man page of the `<command>` (i.e., commands that can be run from shell by a regular user) |
|`man 5 <command>`| Show me the file formats & conventions man page of `<command>` (e.g., configuration files like `passwd`) |
|`man 8 <command>`| Show me	the system administration tools & daemons man page of `<command>` (i.e., commands that require root or other administrative privileges to use) |

---

### Important Shorcuts 

| Syntax | Description |
| ------ | ----------- |
| `Ctrl + Z` | Stop an active program
| `Ctrl + L` | Clear the screen (Note: Useful when `bg` processes generate output |
| `Ctrl + D` | Quit from shell |
| `Ctrl + Alt + F[1-6]` | Switch between virtual consoles [1-6] |

#### Fedora, Gnome 40

| Syntax | Description |
| ------ | ----------- |
|` Ctrl + Alt + Tab` | Select different views |

---

### General user and machine info 

To find out about yourself--and in Linux the machine your working with--,
helps you to achieve anything!

| Syntax | Description |
| ------ | ----------- |
| `who` | Show me who is logged in |
| `who -u` | Show me who is is logged |
| `who -H` | Show me a header to prescribe the info |
| `whoami` | Show me who am I (i.e., prints only the name in `who`) |
| | |
| `hostname` | Show me my computer's host name |
| | |
| `uname` |	Show me the type of system running |
| | |
| `id` | Show me user and group ID |

**Useful examples**

| `who -uH` | Show me who is logged in with a header to prescribe the information | 

**Important Output**

| `tty[x]` | The [x]th virtual console on the monitor connected to the computer |
| `COMMENT`| The name of the remote computer from which a user is logged in |

---

### Orientate where you are! 

Since you found out about yourself, you have to orientate!

---

#### pwd

| `pwd` | Show me the working directory I'm currently at |

---

#### ls 

formula: 

```
ls [option] [file/dir/pattern]
```

| Syntax | Description |
| ------ | ----------- |
|`ls`| List files in the current directory |
|`ls -a`| List me all files (i.e. hidden file, like dotfiles, and non-hidden files) |
|`ls -S`| List me the files sorted by size |
|`ls -t`| List me the files sorted by modification time |
|`ls -F`| List me the files with a file-type indicator (i.e., `*/=>@|`) |
|`ls -l`| List in long format |
| `ls -ld`|	List info about directories (i.e., instead of files) |
| `ls -R` |	List recursively |
| `ls --hide <pattern>` |	List; but hide `<pattern>` |
| `ls --color=auto` | List different file/dir types in different colors	|

**File matching metacharacters**
see also: <https://help.relativity.com/9.3/Content/Relativity/Regular_expressions/Regular_expression_metacharacters.htm>

| Syntax | Description |
| ------ | ----------- |
| `.` | Match any single character |
| `*` | The preceding item will be matched zero or more times |
| `?` | The preceding item is optional and will be matched, at most, once |
| `[a,b,c]` | Match the denoted items within the brackets  |
| `[a-c]` | Match the range of items within the brackets |
| `[a-z]` | Match any letter |

**Useful Examples**

| Syntax | Description |
| ------ | ----------- |
| `ls | wc -w` | Print the number of files in a directory |
| | |
|`ls a*`| List any file that begins with `a` |
|`ls *e`| List any file that ends with `a` |
|`ls *c*`| List any file that contains `c` |
|`ls [a,b,c]*`| List any file that starts with `a,b,c` |
|`ls *[a-z]*`| List any file that contains a letter |

**Useful Output Indicators**

In the `ls` output you might find:

| `./` | Current directory |
| `../` | Parent directory |
| `total` |	The total amount of diskspace of the listed objects| 

---

#### cat

    `cat` produces standard output concetanating files

| Syntax | Description |
| ------ | ----------- |
| `cat <file>` | Show me what `<file>` contains (i.e., print the content of `<file>` as standard output to the screen) |

**Useful Examples**

| Syntax | Description |
| ------ | ----------- |
| `cat <file> | less` | Page through the content of file |
| `cat .bashrc | wc -m` | Count the number of character `file` contains | 

---

#### date

formula

```
date '+%...'
```

See: `man date` to specify (`%...`) the output of the date command. 


| Syntax | Description |
| ------ | ----------- |
| `date` | Show me the current date and time zone |

**Useful Examples**

| Syntax | Description |
| ------ | ----------- |
| `%D` | Show me the date in the %m/%d/%y format |

---

### Navigate the file system!

Once you have your bearings, you will know where to go! But how?

#### cd

| Syntax | Description |
| ------ | ----------- |
| `cd <path>` | Bring me to path! |

**Useful examples**

| `cd $OLDPWD` | Bring me pack to the origin (i.e., before cd-ing to `<path>`)

I found it useful to alias `cd $OLDPWD` to `cb` (change back) to be able to
jump right back to where I left off.

---

### Shape your environment! 

After you've explored your filescape you can shape it!

---

#### Add! (files, directories & symlinks)

| Syntax | Description |
| ------ | ----------- |
| `touch <file>` | Create an empty file |
| | |
| `mkdir <dir>` | Make directory <dir>
| `mkdir -p </dir/subdir>` |	Make parent directory `<dir>` as needed
| | |
| `ln <file_1> <file_2>` |Make links between files |		
| `ln -s <file_1> <file_2>` | Make a symbolic link betwen <file_1> <file_2> |

**Brace Expansion Characters**

| Syntax | Description |
| ------ | ----------- |
|`{s1,s2,..}`| A (space-separated) list |
|`{}{}`| Use brace 1 as prefix for brace 2 |
|`{<START>..<END>}` | Specify the range to be used |

**Examples**

| Syntax | Description |
| ------ | ----------- |
| `touch a_{1,3,5}`	| `a_1 a_3 a_5` |
| `mkdir {a..b}-{1..3}` | `a1/ b2/ c3/` |
| `touch {a..b>}-{1..2}` | `a-1 a-2 b-1 b-2 c-1 c-2`|

---

#### Copy!

```
cp [option] [files/dirs/pattern] [destination]
```

| Syntax | Description |
| ------ | ----------- |
| `cp -r` | Copy recursively |
| `cp -v` | Copy with a verbose message |
| `cp -i` | Copy but prompt before overwriting |
| `cp -f` | Copy and force to overwrite |
| `cp -a` | Copy but maintain time stamps and permissions |

---

#### Move & rename!

```
mv [option] [file/dir/pattern]
```

| Syntax | Description |
| ------ | ----------- |
| `mv <old_file> <new_file>` | Rename `<old_file>` to `<new_file>`|	
| | |
| `mv <file> <path>` | Copy/move file to home directory |	
| `mv <file> ~` | Rename/Move file to home directory |	

---

#### Remove & unlink

```
rm [option] [file/dir/pattern]
```

| Syntax | Description |
| ------ | ----------- |
| `rm <file>` |	Remove or unlink the `<file>` |
| `rm *` | Remove all files in the current directory |	
| `rm -f` | Remove immediately ; don't prompt |
| `rm -i` |	Prompt before every removal |
| `rm -I` | Prompt once before removing more than three files |
| | |
| `rmdir` | Remove an empty directory |
| `rm -r` | Remove a directory and its contents recursively |

---

#### Archiv!

```
tar [option] [output_file/dir/pattern] [input_file/dir/pattern]
```

| Syntax | Description |
| ------ | ----------- |
| `tar -c` | Create a new archive |
| `tar -v` | Give verbose message |
| `tar -f <files>` | Archive `<files>` |

**Useful examples**

| Syntax | Description |
| ------ | ----------- |
| `tar -cvf project.tar project` | Create an archive `project.tar` from `project`
| `tar -zcvf project.tar.gz project` | Create a *compressed* archive `project.tar` from `project`

---

#### History & command line recall

| Syntax | Description |
| ------ | ----------- |
| `history` | Show me my command history |
| | |
| `! - 2` | Run the penultimate command from history |	
| `!<n>` | Run command `<n>` from my command history |
| `!!` | Run previous command from history file |	
| `!?<string>?` |	Run command from histroy file containing `<string>` |	
| | |
| `fc <number(s)>` | Display command(s) from history; execute `<number>` afterwards |

---

### Sort

Sorts lines of text files

| Syntax | Description |
| ------ | ----------- |
| sort -f |	Sort files ignoring upper an lowercase |

---

### Alias

formula: 

```
alias <shortcut>='<command><option>'
```

| Syntax | Description |
| ------ | ----------- |
| alias | Show me all my aliases |

---

#### Command line completion

formula: 

```
<symbol><TAB>
```

| Syntax | Description |
| ------ | ----------- |
| `<regular char><TAB>` | Complete with a Command, alias or function name |
| `@<TAB>` | Complete with a hostname (..from `/etc/hosts`) |
| `~<TAB>` | Complete a username (e.g., root) |
| `$<TAB>` | Complete with a shell variable |

---

### Permissions! 

A filedom flourishes more quickly under permission!

---

#### Permission sets

There are what I call *letter file mode bits* and the normal *numerical file
mode bits*.

**Object indicators**

| Syntax | Description |
| ------ | ----------- |
| -	| File indicator	
| d	| Directory indicator	
| l	| Symbolic link
	
**File mode bits** 

| Syntax | Description |
| ------ | ----------- |
| `u`| Permissions for the user |		
| `g`| Permission for the (assigned) group |
| `o`| Permissions for others |		
| `a`| Permissions for all |
|||
| `+` | Turn on permission |
| `-` | Turn on permission |
|||
| `r`| Readable |
| `w`| Writable |	
| `x`| Executable |
| `s`| User can run but only root can execute |
| `t`| Sticky bit is set for directory |
|||
| `4` | Readable | 
| `2`| Writeable |
| `1`| Execute permission |
| `0`| No permission |

---

#### chmod

    `chmod` changes file mode bits.

- Numerical formula: 

```
chmod <option> <filemodebits> <pattern>
```

- Literal formula: 

```
chmod <option> <ugoa><+-><rwxst> <pattern>
```

| `chmod` | Change permission sets of files | 
| `chmod -R <dir>`  | Change `<dir>`'s permission set recursively|
| `chmod -v <files>`  | Verbosely change `<files>`'s permission set|

**Useful examples**

| `chmod 664 <file>` | Default file permission |
| `chmod 666 <file>` | Full open file permission |
| `chmod 775 <dir>` | Default dir permission |
| `chmod 777 <dir>` | Full open dir permission |

---

#### chown

    `chown` changes file ownership

```
chown <option> <user,group> <pattern> 
```

```
chown <option> <user>:<group> <pattern> 
```

Note: Here we make `<user>` *and* `<group>` the new owner of files

| Syntax | Description |
| ------ | ----------- |
| `chown` | Make a user/group new owner of some files | 
| `chmod -R <dir>`  | Change file ownership recursively |

---

#### umask

    `umask` sets default file permissions

formula:

```
umask <umask_value> ; touch/mkdir <file/dir>
```

| Syntax | Description |
| ------ | ----------- |
| `umask` |	Display the default file permissions |

**Useful examples**

| Syntax | Description |
| ------ | ----------- |
| `umask 000` | Full open file/dir permission | 
| `umask 002` | Default file/dir permission | 
| `umask 022` | Root file/dir permission | 

---

### Shell variables

formula:

```
export <VAR>=<value(s)>
```

| Syntax | Description |
| ------ | ----------- |
| `set` | Set a shell option |
| `export` | Set an attribute for a shell variable |
| `echo` | Print text on the screen (..useful to display the values of shell variables) |
| `printenv` | Get a full list of all environment variables (..use with `| grep=...`) |
| `declare` | Get a list (messy) of environmental variables	(..use with `| grep=...`) |

**Useful examples**

| Syntax | Description |
| ------ | ----------- |
| `set -o vi` | Set vi to edit shell command lines (Note:..put in .bashrc for permanent change) |
| `export EDITOR=nvim` | Set the attribute 'nvim' for the shell variable `EDITOR` 
| `echo $EDITOR` | Show me the value behind the `EDITOR` shell variable

**Important shell variables**

For a full list, see: <https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables">https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables>	

| Syntax | Description |
| ------ | ----------- |
| `$BASH` |	The full pathname of the bash command |
| `$BASH_VERSION` |	The version of the bash command |
| `$HISTCMD` | The number of the current command in the history list |
| `$HISTFILE` |	The location of the history file |
| `$HISTSIZE` |	The number of history entries |
| `$HOME` |	The path of the home directory |
| `$HOSTTYPE` |	The computer architecture |
| `$OSTYPE` | Current OS |
| `$PATH` | The current path |
| `$PROMPT_COMMAND` | The command which runs each time before prompt is displayed |
| `$PS1` | The prompt of my shell |
| `$PWD` | The working directory |	
| `$RANDOM` | A random number between 0 and 99999 |
| `$SHELL` | The current shell	
| `$TMOUT` | The time (without receiving input) till shell goes idle (exits) (..useful to set as a security feature) |
| `$USER` | The user name |
| `$OLDPWD` | The working directory before cd-ing into the current one |

---

## Sourcing files

| Syntax | Description |
| ------ | ----------- |
| source | Read and execute files from current shell |

---

### Echo & file matching metacharacters

| Syntax | Description |
| ------ | ----------- |
| `echo` | Print text on the screen (..useful to display the values of shell variables) |
| `echo -n` |	Do not output the trailing newline |

---

## File Re-direction metacharacters

| Syntax | Description |
| ------ | ----------- |
| `<command> > <file>` | Direct the output of `<command>` to `<file>` -- overwrite at the end |
| `<command> >> <file>` | Direct the output of `<command>` to `<file>` -- append at the end |
| `<command> 2> <file>` | Redirect a `<command>`'s error message and output to `<file>` |
| `<command> &> <file>` | Redirect a `<commands>`'s error message and output to `<file>` |

Note: Useful with `mail`!

### Mail me!

| Syntax | Description |
| ------ | ----------- |
| `mail` | Send mail message to a local account |

---

### Search & Find!

Confucius says: If you cannot `ls` the content of a directory you won't `find`
anything within! This implies:

| Syntax | Description |
| ------ | ----------- |
| `find` |  Find files you have access to (e.g., user-readable files) |
| `sudo find` |  Find all files |

**File size characters**

| Syntax | Description |
| ------ | ----------- |
| `b` | Bytes |
| `k` | Kilobytes |
| `M` | Megabyte |
| `G` | Gigabyte |

#### Between-file search!

Note: There are (at least) two options `locate` and `find`. `locate` is faster,
since it is no live file search. It locates command in the `mlocate` data base. 
Thus you need to keep the data base up-to-date!

---

##### locate

formula:

```
locate <option> <pattern> 
```

| Syntax | Description |
| ------ | ----------- |
| `locate <string>` | Which searches for a string in the `mlocate` database |
| `locate -i <file>` | Locate &lt;file&gt; ignoring case distinctions |
| `updatedb <string>` | Updates the mlocate database (i.e. this is done every day automatically, but if your downloading new stuff it can be useful to know how to update!) |

---

##### find

    `find` finds a set of files within the file system live

formula:

```
find <path> <action> <pattern> 
```

Note: We call the one word options with a single `-` find *actions* 

find	command	Find user-readable files/dirs\(^*\) live&nbsp;	\(^*\)below that poing in the fs	

| Syntax | Description |
| ------ | ----------- |
| `find <pattern>` | Find `<pattern>` below my current directory | 
|||
| `find -ls` | Find and list long (Note: Gives you the permission set!) |
|||
| `find <path> -type d` |	Find only directories |
| `find <path> -type f` |	Find only files |
|||
|`find -iname <pattern>`|	Find a case insensitive `<pattern>` below `<path>` |
|`find -name <pattern>`|	Find a case sensitive `<pattern>` below `<path>` |
|||
| `find -size +<size1> -size -<size2>` | Find files between `<size1>` and `<size2>`
| `find -size +<size>` | Find files above `<size>`| 
| `find -size -<size>` | Find files below `<size>`| 
|||
| `find -perm <filemodebit>` | Find files that match the permission set as a whole |
| `find -perm -<filemodebit>` | Find files that match *all*  permissions (i.e. user AND group AND others) |
| `find -perm /<filemodebit>` | Find files that match *all*  permissions (i.e. user OR group OR others) |
|||
| `find -user <user>` | Find files by `<user>` (I.e.: the owner of the file) |
| `find -user <user>` | Find files by `<user>` (I.e.: the owner of the file) |
|||
| `find -user <user>` | Find files by `<user>` (I.e.: the owner of the file) |
| `find -group <group>` | Find files by `<group>`|
|||
| `find \(... -or ...\)` | Find by `...` or `...`|
| `find \(... -and ...\)` | Find by `...` and `...`|
| `find -not ...`| Find all files that are not `...` (e.g. owned by user/group) |		
|||
| `find -exec command {} \;` | Execute <command> on all files found |
| `find -ok command {} \;` | Execute <command> on all files found and query if the action is permitted |
|||
| `find -cmin -<minutes>` | Find files that were changes x `<minutes>` ago |
| `find -ctime -<days>` | Find file that were changes x `<days>` ago |
| `find -amin -<minutes>` | Find files that were accessed x `<minutes>` ago |
| `find -atime -<days>` | Find file that were accessed x `<days>` ago |
| `find -mmin -<minutes>` | Find files whose meta data were accessed x `<minutes>` ago |
| `find -mtime -<minutes>` | Find files whose meta data were accessed x `<days>` ago |

**Useful examples**

| `find -type f -perm /002`	| Find every `<file>` that is writeable for others (Note: useful to find files which should only be writeable for root) |
| `find -type f -ok rm {} \;` | Find & delete all files that match a pattern |

---

##### grep

    `grep` starts a within file, text, or standard output search for matching lines

Search formula:

```
grep <option> <pattern> <file>
```

Standard output formula:

```
<command> | grep <option> <pattern> 
```

| Syntax | Description |
| ------ | ----------- |
| `grep -i "[pattern]"` | Within `file`, case-insensitively show me all lines that match `[patterns]` |	
| `grep --color "[pattern]"` | Within `file`, show me all lines that match the `"[pattern]"` in color |
| `grep -r "[pattern]" <dir>` | Within `dir` recursively find me all lines that match the [patterns] and all it's files |
| `grep -v "[patterns]" <file>` | Within `file`, show me all lines; that *don't* match the `[patterns]` |	

**Useful examples**

| Syntax | Description |
| ------ | ----------- |
| `grep -rl "[pattern]" <dir>` | Within `dir` find me all files where all the lines match the `[pattern]` |

---

#### Command essentials

| Syntax | Annotation | Description |
| ------ | ---------- | ----------- |
| `;` (semicolon) |	Command expansion character	| Run a sequence of commands | 
| `$` (dollar sign) | Command substitution | Run a sequence of commands | 
| `&` (ampersand) | command manipulation | Have the command run in the `bg` |

Expansion formula:

```
<command_1> ; <command_2> ; ....
```

Substitution formula:

```
<command> $( <commands> ) 	
```

Manipulation formula:

```
<command> | <command> &
```

---

### Transform characters, words and files

| `tr` | Translate or delete characters		f
| `cut` | Remove sections of lines of files and text


**Useful examples**

```
for file in * ; do
f=`echo $file | tr [:blank:] [_]`
[ "$file" = "$f" ] || mv -i -- "$file" "$f"
done
```

```
grep /home /etc/passwd | cut -f6 -d':' -	
```

#### Count characters, words and files

| Syntax | Description |
| ------ | ----------- |
| `wc -w` | Print the word count | 
| `wc -m` | Print the char count | 

---

### Managing Running Processes!

#### Inspect running processes

I familiarized with three ways to manage running processes:

1. `ps`, `(re)nice`, and `fg/bg`
2. `top`
3. `gnome-system monitor`

---

#### ps

    ps snapshots all current processes

| Syntax | Description |
| ------ | ----------- |
| `ps` | Show me a snapshot of all running processes (time, PID, command) |
| `ps u` | Show me a snapshot of all my users running processes (programs, resources, user) |
| `ps ux` | Fully list all (including background processes) my user processes running on your system |	
| `ps aux` | Fully list all processes (including background processes) for *all* users (especially root) on the system | 

Note: None of them will show you the nice values  that the

**Standard Syntax**

formula:

```
ps -eo <argument>
```

| Syntax | Description |
| ------ | ----------- |
| `ps -e` | Show me *every* running process on the system (but exclude background processes) |
| `ps -eo <argument>` | Show me *every* running (`fg`) process on the system in a given format |
| `ps -eo comm` | Show me the command name of *every* running (`fg`) process on the system |
| `ps -eo user` | Show me the group associated with *every* running (`fg`) process on the system |
| `ps -eo group` | Show me the group associated with *every* running (`fg`) process on the system |
| `ps -eo uid` | Show me the user ID (which identifies the user to the system) for every running process |
| `ps -eo uid` | Show me the group ID (which identifies the group to the system) for every running process |
| `ps -eo pid` | Show me the process id of *every* running (`fg`) process on the system |
| `ps -eo rss` | Show me the resident memory (the memory actually used by a process) used for each process
| `ps -eo vsz` | Show me the virtual memory (the amount of space allocated to a process) allocated |
| `ps -eo <argument> --sort=<argument>` | ...and sort by the lowest `<argument>` |
| `ps -eo <argument> --sort=-<argument>` | ...and sort by the highest `<argument>` |

**Useful output identifier**

`ps` can give the following output:

| Syntax | Description |
| ------ | ----------- |
| `+ (STAT)` | Process running in the foreground |
| `- (STAT)` | Process running in the background |
| `RSS` | Resident Set Size (i.e.	"Used size of the program in memory!")" |
| `TIME` | Cumulative System time used |

## jobs

| Syntax | Description |
| ------ | ----------- |
| `jobs` | Show me which processes run in the background |

#### Manage running processes

To manage running process you need to know how to put them in the background
and bring them back to the foreground. Despite that, you need to be fluent in
signaling processes.

---

##### fg & bg 

    Rund a process in the foreground or background

| Syntax | Description |
| ------ | ----------- |
| `fg %<command>` | Bring `<command>` back to `fg` |
| `bg %<command>` | Put `<command>` in the `bg` |
| `fg %--` | Bring the penultimate back to the `fg` |
| `bg %--` | Run the penultimate command in the `bg` |
| `fg %<n>` | Bring the `<n>`-th command back to the `fg` |
| `bg %<n>` | Put the `<n>`-th command in the `bg` |
| `fg %?<pattern>` | Bring a command including `<pattern>` back to `fg` (Note: string must be unambiguous) |
| `bg %?<pattern>` | Run a command including `<pattern>` in the `bg` (Note: string must be unambiguous) |

##### Signals!

| Name | Number | Description |
| ------ | ---- | ----------- |
| `SIGHUP` | `1` | Reread a processes config file |
| `SIGTERM` | `9` | Kill a process immediately |
| `SIGTERM` | `15` | Terminate a process cleanly |
| `SIGSTOP` | `17` | Stop a process |
| `SIGCONT` | `19` | Continue a process |

---

##### kill

    "Signal" (applies a *signal* to) by a process by identifier 

Number formula:

```
kill <SIGNAL_number> <PID>
```

Name formula:

```
kill -<SIGNAL_name> <PID>
```

**Useful examples**

```
kill -SIGKILL 19381
kill 9 19381
```

---

##### killall

    "Signal" (applies a *signal* to) a process by name 

Number formula:

```
killall <SIGNAL-number> <command>
```

Name formula:

```
killall -<SIGNAL_name> <command>
```

**Useful examples**

```
killall -SIGTERM nvim
killall 15 nvim 
```

---

##### nice

    `Starts process with a given priority`

formula:

```
nice -n <+-><priority> <command>
```

| Syntax | Description |
| ------ | ----------- |
| `nice -n +<n>` | Start a process with the given nice integer `<n>` |

---

##### nice

    `Alter the priority of a given process`

formula:

```
nice -n <+-><priority> <PID>
```

| Syntax | Description |
| ------ | ----------- |
| `renice -n +<PID>` | Add `<n>` to the processes priority |
| `renice -n -<PID>` | Subtract `<n>` from the processes priority |

    The nicer rule: The nicer a process is; the less CPU attraction it gets!

---

##### cgroups

`cgroups` is an advanced concept. More precisely, it is a tool to limit the
usage by selected pocesses,	i.e.: cpu assignment (cpuset), processor
schedueling (cpi).


| Syntax | Description |
| ------ | ----------- |
| `man cgroups` | Show me the `cgroups` man page |

---

### Inspect & manage running processes!

#### top

| Key combo | Description |
| ------ | ----------- |
| `k <PID> 9` | Kill the process `<PID>` outright |
| `k <PID> 15` | Kill the process `<PID>` cleanly |
| | |
| `r <PID> -20` | Renice the process `<PID>` to have highest priority |
| `...` | `...` |
| `r <PID> -1` | Renice the process `<PID>` to have high priority |
| `r <PID> 0` | Renice the process `<PID>` to have normal priority |
| `r <PID> 1` | Renice the process `<PID>` to have low priority |
| `...` | `...` |
| `r <PID> 19` | Renice the process `<PID>` to have lowest priority |
| | |
| `M` |	Sort by memory usage (instead of CPU) |
| `P` |	Sort by CPU usage (instead of memory usage) |
| `R` |	Reverse sort your output |
| | |
| `u <user>` | Show only `<user>` processes |
| `g <group>` | Show only `<group>` processes |

---

#### gnome-system-monitor

If you use `Gnome` as DE you can also use a comprehensive tool for processes,
ressources and fs: the `gnome-system-monitor`.

| Key combo | Description |
| ------ | ----------- |
| `Ctrl + S` |	Stop the process (i.e., pause it) |
| `Ctrl + C` |	Continue the process |
| `Ctrl + K` |	Kill the process (i.e., terminate it outright -- SIGKILL (9)) |
| `Ctrl + E` |	End the process (i.e., terminate it cleanly -- SIGTERM (15)) |

---

### Shell scripting!

There are basically two ways to launch a shell script:

| Syntax | Description |
| ------ | ----------- |
| bash `<script>` | Launches the shell `<script>` from the console |
| `#!/bin/bash` | Identifier within the script | 

Note: Please make sure, the script is executable! E.g., using `chmod +x <file>`

    Important: Bash generally uses *untyped variables*. This means variables
    are strings unless you `declare` it otherwise!

---

#### Debugging

| Syntax | Description |
| ------ | ----------- |
| `bash -x <script>` | Display each command executed (Note: set it near beginning of the script) |

---

#### Misc

| Syntax | Description |
| ------ | ----------- |
| `\` (backslash) |	Interpret one char literally |		
| `#` (pound sign) | Comment |
| `'` (single quotes)| Put somethings in single quotes interprets a set of characters literally |	
| `(backticks)` | Put something in backticks	runs a command only when a variable is set not each time the variable is read. This improves efficiency! |	

**Useful examples**

```
#!/bin/bash
# Executes date only once!
MYDATE=`date %D`

...script...

```

---

##### Reading command-line input

| Syntax | Description |
| ------ | ----------- |
| `read <variable(s)>` | Read command-line input and store it in `<variable(s)>`		
| `read -p "prompt msg" <variable(s)>` | Prompt for infos, read and store them in `<variable(s)>`

**Useful examples**

```
#!/bin/bash
read WORD
echo "$WORD, $WORD!"
$ ~/myfile

#!/bin/bash
read -p "Enter: name & adjective " NAME ADJ
echo "$NAME is $ADJ"
$ ~/myscript 
Enter a name and an adjective 
Bart hair
```
---

#### Arithmetic

| Syntax | Description |
| ------ | ----------- |
| `'$[arithmetic - operation]'` | Pass arithmetic result to a command |
| `let` | Evaluate arithmetic expressions |
| `bc` | Arbitrary precision calculator	|
| `expr` | Evaluate (logical/mathematical) expressions |
| `$((--I))` | Incrementally decrease `<I>` by 1 |
| `$((I++))` | Incrementally increase `<I>` by 1 |


**Useful examples**

```
# Pass arithmetic result to a command
echo $[5-3]	2	

# Evaluate arithmetic expressions
# No spaces!	
BIGNUM=1024
let RESULT=$BIGNUM/16 ;
echo $RESULT

BIGNUM=1024<br>
RESULT=`echo "$BIGNUM / 16" | bc` ;
echo RESULT	

# Evaluate (logical/mathematical) expressions
# Requires whitespaces!
BIGNUM=1024
RESULT=`expr $BIGNUM / 16` ; 
echo $RESULT

I=0 ; echo "I + 1 = $((++I))"	
I=0 ; echo "I - 1 = $((--I))"
```
---

#### Fundamentals

formula:

```
NAME=value
```
	
| Syntax | Description |
| ------ | ----------- |
| `NAME=value` | Assign variable `<NAME>` the `<VALUE>` `no spaces!`|

---

#### Shell (positional) parameters

| `$@` | Give me all arguments entered at the command line |
| `$#` | Give me the the n° paramaters in my script |
| `$0` | Give me the name used to invoke my script |		
| `$?` | Give me the exit status of the last command |
| `$<n>` | Give me the value of the `n-th` command-line argument |


**Examples**

```
    # Give me all arguments entered at the command line!
    #!/bin/bash
    echo "all arguments are: $@"<br>$ 
    $ ~/myscript foo bar	
    all arguments are: foo bar

    # Give me the the n° paramaters in my script |
    #!/bin/bash
    echo "My script was given $# parameters"
    $ ~/myscript foo bar	
    My script was given 2 parameters	linux_01_code

    # Give me the name used to invoke my script
    #!/bin/bash
    $ echo "the command is called '$0'"
    ~/ myscript foo	
    the command is called '/home/steven/myscript`	

    # Give me the exit status of the last command
	#!/bin/bash
    echo "The exit status is: $?" <br>
    if [ $? -eq 0 ] ; then
    echo "Script ran successfully!" 
    fi
    $ ~/myscript	
    The exit status is: 0 Script ran successfully!	

    #Give me the value of the `n-th` command-line argument
    #!/bin/bash
    echo "the first argument is $1 the second $2"
    $ ~/ myscript foo bar	
    the first argument is foo, the second bar
```

---

#### Conditional execution

##### if...then...

```
if [ cond ] ; then
    expr1
fi
```

Note: Spaces in `[ cond ]` are mandatory

##### if...then...else

```
if [ cond ] ; then
    expr1
else

elif [ cond ] ; then
    expr2
else
    expr3
fi	

```

Note: Spaces in `[ cond ]` are mandatory!

---

##### Alternative one-line if...then...else

`[ cond ] && <action> || <action>`

---

##### for...do...

```
for VAR in LIST
do
    body
done
```
---

##### until...do...

Until TRUE do ... ; if TRUE stop!

```
until [ cond ]
do
    body
done
```

Note: Spaces in `[ cond ]` are mandatory

---

##### while...do...

while TRUE do ... ; if FALSE stop!

```
while [ cond ]
do
    body
done
```

Note: Spaces in `[ cond ]` are mandatory!

---

##### case

Nested if-then-else statements

```
case VAR in
Result1)
     body;;
Result2)
    body;;
...
*)
    body;;
esac
```

Note: Spaces in `[ cond ]` are mandatory!

---

#### Test expression operators 

| Syntax | Description |
| ------ | ----------- |
| `help test` | Get help on test expression operators | 
| | |
| `[ ! cond ]` | Not [cond]!		
| `[ cond ] && <action>` | If [cond]=TRUE then `<action>` |		
| `[ cond ] || <action>` | If [cond]=TRUE then `<action>` |		
| `[ -n ;string ]` | Is the length of <string> 0 bytes? 
| `<sting> = <string>` | Are both *strings* equal?	

**Useful examples**

```
#!/bin/bash
if [ ! -e "$TODOLIST" ] ; then 
touch ~/.todolist
echo "touched todolist"
fi

#!/bin/bash
[ $# -ge 3 ] && echo "There are more than 3 cmd-line args"

#!/bin/bash
[ $# -ge 3 ] || echo "There are less than 3 cmd-line args"

#!/bin/bash
FILE="~/foo.txt"
if [ -n "$FILE" ] ; then
echo "$FILE is greater than 0 bytes"
fi

#!/bin/bash
STRING="friday"
if [ "$STRING" = "friday" ] ; then
echo "Yippie, it's friday!"
fi	
```
---

#### Bash parameter expansion

| Syntax | Description |
| ------ | ----------- |
| `${VAR}` | The longform of $VAR |		
| `{var:-value}` | If <var> is empty or unset, expand it to `<value>` |
| `${var#pattern}` | Chop the `<shortest>` match for `<pattern>` from the *front* of `<vars>` value	|
| `${var##pattern}`| Chop the `<longest>` match for `<pattern>` from the *front* of `<vars>` value |
| `${var%pattern}`| Chop the `<shortest>` match for `<pattern>` from the *end* of `<vars>` value |
| `${var%%pattern}`| Chop the `<longest>` match for `<pattern>` from the *end* of `<vars>` value |

**Useful examples**

```
#!/bin/bash
read -p "Enter a word!" WORD 
echo "$WORD = ${WORD}"	

#!/bin/bash
FOO="Example" ; FOO=${FOO:-"Not Set"}
echo $FOO

#!/bin/bash
MYFILE=/home/steven/foo.txt
<br>FILE=${MYFILE##*/} ; echo $FILE

#!/bin/bash
MYPATH=/home/steven/foo.txt
DIR=${MYPATH%/*} ; echo $DIR

#!/bin/bash
MYPATH=/home/steven/foo.txt
EXTENSION=${MYPATH#*.} ; echo $EXTENSION

#!/bin/bash
MYPATH=home/steven/foo.txt
MYHOME=${MYPATH%%/*} ; echo $MYHOME	
```

---

## Becoming a Linux System Administrator


### Directories & files

I got most of the information from the Linux foundation page
(https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.html). Since Fedora uses
the File System Hierarchy Standards (FHS) its a great source.

| Syntax | Description |
| ------ | ----------- |
| `/` | Root (directory) of the fs |	
|||
| /root | Home directory for the root user |
| `/var` | Variable data files	(e.g. administrative and logging data, spool directories &amp; files) |
| `/mnt` | (Mount point for temporarily mounted filesystems) |
| `/opt` | Add-on application software packages (3rd-party) |
| `/media` | Mount point for removeable media |
| `/srv` |	Data for system services |
| `/tmp` | Temporary files	(i.e., lock files and temporry data storage) |
| `/lib` | Essential shared libraries and kernel modules (e.g., the C programming code library needed to boot the system and run the commands in the root filesystem) | 
| `/proc` | Pseudo filesystem documenting the kernel and processes as text files (i.e., the information base for commands displaying running processes) |
| `/sbin`	|  Sytem binaries (i.e., commands to boot, restore, recover or repair the system -- in addition to binaries in /bin)	| 
| `/usr`	| (Multi-)user utilities and applications (i.e., everything available to the Linux use, like binaries, their documentation, libraries, header files)
| `/bin` | Essential user command binaries (i.e., commands for the system admin and non-privileged users, like bash, csh, cp, mv, rm, cat, ls) |
| `/boot` |	Static bootloader files	(e.g. Linux kernel, initrd)	
| `/dev` |	Device files (e.g., disks, cpu, memory, udevd) |
| `/etc` |	Host-specific system configurations	(i.e., the major location of system-wide config files |
|||
| `/etc/cron*` | Place, where services and applications generally add cron job files	\(^*\)<b>cron.d/</b> cron.daily cron.weekly cron.montly			linux_01_code
| `/etc/crontab` | Set time for running automated tasks and varibles (Note: associated with the cron facility |
| `/etc/cups` | Global config files for CUPS (e.g., default print server) |
| `/etc/default/grub` | Configures <i>update-grub</i>\(^*\)&nbsp;	\(^*\)for generating&nbsp;<em>/boot/grub/grub.cfg</em>			linux_01_code
| `/etc/exports` |	Lists local directories which can be shared via NFS |
| `/etc/fstab` | Decides where to mount all partitions available to the system |
| `/etc/hosts` | Maps IP addresses to their hostnames (i.e., to store private networks and names of computers on LAN) |
| `/etc/hostname` | Sets the hostname for the machine |	
| `/etc/passwd` | Contains user account info (e.g., home, shell..)
| `/etc/shells` | Lists all avalable shells	|
| `/etc/systemd` | Configuration files for Systemd |
| `/etc/skel` |	Global configs copied to any *new* user's /home/user (i.e., when he/she is added to the system) |
| `/etc/sudoers` | Manages (root) users and group priveleges using sudo	|	
| `/etc/xinetd.conf` | Configures xinetd |
| `/etc/X11` | Config files for the X window system (xorg) |	
| `/etc/X11/xorg.conf` | Makes your computer usable with X |
|||
| `/etc/bashrc`	| (System-wide) commands every non-login shell executes	- executes: @1st login, opening<br>- overwritten by ~/.bashrc			linux_01_code
| `/etc/profile` | (System-wide) commands the log-in shell executes	(Execute: @1st login & overwritten: by `~/.profile`. Use: location of mailbox, size of history files; i.e., system-wide environment variables) and startup programs |	
| `/etc/profile.d` | Dir from which /etc/profile gathers shell settings (execute: @1st log in |
|||
| `/var/ftp` | FTP directory |
| `/var/www` | Web server directory |
| `/var/log/boot.log` | Boot messages gathered by rsyslogd (Note: replaced by Systemd) |
| `/var/log/messages` | General system infos gathered by rsyslogd (Note: replaced by Systemd) |
| `/var/log/secure` | Security related messages gathered by rsyslogd (Note: replaced by Systemd) |

run/media/<user>	dynamic system directory	Mountpoint for USB devices	\(^*\)instead of /mnt			linux_01_code

/usr/sbin	system directory	Commands to manage the user accounts, holding files open, daemon processes, printers, service requests		ls /usr/sbin	wpa_supplicant* <br>mkfs.ext3*<br>cupsd<br>sshd	linux_01_code

/usr/share/man/man8	system folder	A list of all administrative commands	I.e.: Intented for the system administrator	ls /usr/share/man/man8 | less	clock.8.gz <br>cockpit-tls.8.gz&nbsp;	linux_01_code



/lib/modules	system directory	Kernel modules		ls /lib/modules | tail	5.15.8-200.fc35.x86_64/	linux_01_code

{{c1::httpd}} {{c1::-t}}	command and option	Check the sanity of Apache config\(^*\)	\(^*\)before the web server is started			Cloze

testparm	command	Check the sanity of samba.conf				linux_01_code

/home	system directory	User Home Directories	Major location of&nbsp;<i>personal</i>&nbsp;config files	ls ~/.*	.R .ssh .local .vim&nbsp;	linux_01_code

~/.bash_profile	system file	(User) commands the log-in shell executes	Execute: @1st log-in<br>Use: enviornment variables	<a href="https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables">https://gnu.org/software/bash/manual/bash.html#Shell-Variables</a>		linux_01_code



/dev/shm	dynamic system directory	The system's virtual memory file system		df	tmpfs&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8131940&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 752&nbsp;&nbsp; 8131188&nbsp;&nbsp; 1% /dev/shm&nbsp;<br>/dev/nvme0n1p3 481666048 44402684 436272804&nbsp; 10% /home <br>/dev/nvme0n1p2&nbsp;&nbsp;&nbsp; 999320&nbsp;&nbsp; 249504&nbsp;&nbsp;&nbsp; 681004&nbsp; 27% /boot	linux_01_code


tail	command	Output only the <i>last</i> parts of a file/standard output\(^*\)	\(^*\)default is 10	ls /etc/modules | tail	5.14.16-301.fc35.x86_64/ <br>5.14.17-301.fc35.x86_64/ <br>5.14.18-300.fc35.x86_64/&nbsp;	linux_01_code

head	command&nbsp;	Output only the <i>first</i> parts of a file/standard output\(^*\)	\(^*\)default is 10	journalctl --list-boots | head&nbsp;	-52 e26fdjdahjhdas 2021-09-07 14:42:45 CEST&nbsp;	linux_01_code








/dev/sd<...>	dynamic system directory	USB devices		lsblk	sda&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8:0&nbsp;&nbsp;&nbsp; 1&nbsp; &nbsp; &nbsp;15G&nbsp; 0 Massstorage	linux_01_code


~/.bashrc	system file	(User) commands every non-login shell executes	Executes: @login, opening<br>Use: aliases			linux_01_code

~/.bash_logout	system file	(User) commands executed each time you log out				linux_01_code


<ol><li>{{c1::usr/local/bin}}</li><li>{{c1::usr/local/sbin}}</li></ol>	system directory	Directories to add my commands	\(^* \because\) directories are usually added to $PATH, can overwrite commands of the same name	ls /usr/local/bin		Cloze

<ol><li>{{c1::/usr/local/bin}}</li><li>{{c1::/usr/local/sbin}}</li><li>{{c2::/opt/bin}}</li></ol>	system directories	3rd party commands\(^*\)	\(^*\)not included with the Linux distro	ls /usr/local/bin		Cloze

system directories	<ol><li>{{c1::/usr/local/bin}}</li><li>{{c1::/usr/local/sbin}}</li><li>{{c2::/opt/bin}}</li></ol>	3rd party commands\(^*\)	\(^*\)not included with the Linux distro	ls /usr/local/bin		Cloze



## Becoming someone else

| Syntax | Description |
| ------ | ----------- |
| su | Open a shell as a new user |
| sudo su | Open a shell as root (Attention: permanently!) |
| su - <user> | Open a shell as <user> |
| | |
| logout | logout from a shell |
| exit | Quit from a shell |


## System Admin




dmesg	command	List detected hardware and drivers loaded	e.g. kernel, boot_image, usb, ethernet	dmesg | grep "wlp4s0"&nbsp;	[94262.147773] wlp4s0: authenticate with 18:82:8c:c1:0a:be <br>[94262.169543] wlp4s0: send auth to 18:82:8c:c1:0a:be (try 1/3)&nbsp;	linux_01_code

df	command	Report file system disk space usage\(^*\)	\(^*\)and mountpoints	df	/dev/nvme0n1p3&nbsp; 44402668 436272820&nbsp; 10% /home <br>/dev/nvme0n1p2&nbsp; 249504&nbsp;&nbsp;&nbsp; 681004&nbsp; 27% /boot <br>/dev/nvme0n1p1&nbsp; 23444&nbsp;&nbsp;&nbsp; 589740&nbsp;&nbsp; 4% /boot/efi&nbsp;	linux_01_code


at	command	Run a command at a specific time		echo "command_to_be_run" | at 6:50	"hello"	linux_01_code

passwd_timeout=0	/etc/sudoers	Force root/user to always enter sudo\(^*\)	\(^*\)no time-out for password	echo "passwd_timeout=0" >&gt; /etc/sudoers		linux_01_code

du	command	Estimate file space usage		find $Home -size +1G -exec du {} \;	1089072&nbsp;&nbsp;&nbsp; ./Videos/taichi/lesson1.mp4&nbsp;	linux_01_code

http://<ip_addr>:9090	web address	Cockpit		firefox https://192.168.2.143:9090		linux_01_code

{{c1::ip}} {{c1::addr}}	command	Get device's IP address	Note: ifconfig is opbsolete	ifconfig	3: wlp4s0: noqueue state UP group default qlen 1000 <br>&nbsp;&nbsp;&nbsp; link/ether bc:a8:a6:d0:a8:22 brd ff:ff:ff:ff:ff:ff <br>&nbsp;&nbsp;&nbsp; inet <u>192.168.2.143</u>/24	Cloze



grubby	root command	Changes kernel boot parameters	\(^*\)recommended way	grubby --args=<NEW_PARAMETER> --update-kernel=/boot/vmlinuz-5.11.13-300.fc34.x86_64		linux_01_code


inst.ks=<code>\(^*\)	boot option	Identify a kickstart file	\(^*\)<a href="https://access.redhat.com/documentation/en-en/red_hat_enterprise_linux/5/html/installation_guide/s1-kickstart2-startinginstall">https://access.redhat.com/documentation/en-en/red_hat_enterprise_linux/5/html/installation_guide/s1-kickstart2-startinginstall</a>	inst.ks=ftp://ftp.example.com/allks/ks.cfg		linux_01_code

inst.repo=<code>\(^*\)	boot option	Identify software repository location	\(^*\)<a href="https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/installation_guide/chap-anaconda-boot-options">https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/installation_guide/chap-anaconda-boot-options</a>	inst.repo=hd:dev/sda1:/myrepo		linux_01_code

inst.vncconnect=hostname[:port]	boot option	Connect to VNC <i>client</i> <hostname> (and optional &lt;port&gt;)		inst.vncconnect=192.168.0.99:1		linux_01_code

journalctl	command	View <i>all</i> messages from the systemd journal		journalctl | less	Sep 07 14:33:35 fedora kernel: Linux version 5.11.12-300	linux_01_code

lsblk	command	List block devices\(^*\)	\(^*\)Hard disks, USB, CD-ROMs	lsblk	sda&nbsp; &nbsp;8:0&nbsp;&nbsp;&nbsp; 1&nbsp;&nbsp;&nbsp;&nbsp; 0B&nbsp; 0 disk  <br>zram0&nbsp; 252:0&nbsp;&nbsp;&nbsp; 0&nbsp;&nbsp;&nbsp;&nbsp; 8G&nbsp; 0 disk [SWAP] <br>nvme0n1&nbsp; 259:0&nbsp;&nbsp;&nbsp; 0 476.9G&nbsp; 0 disk  <br>├─nvme0n1p1 259:1&nbsp;&nbsp;&nbsp; 0&nbsp;&nbsp; 600M&nbsp; 0 part /boot/efi&nbsp;	linux_01_code


lscpu	command&nbsp;	List processor infos		lscpu	Architecture: x86_64<br>CPU(s): 4&nbsp;<br>Model name: Intel(R) Core(TM) i7-7500U CPU @ 2.70GHz&nbsp;	linux_01_code

lsmod	command	List loaded modules\(^*\)	\(^*\)I.e: code to flexible extent the kernel	lsmod | grep intel	intel_xhci_usb_role_switch&nbsp;&nbsp;&nbsp; 16384&nbsp; 0 <br>intel_pch_thermal&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 20480&nbsp; 0&nbsp;	linux_01_code

lspci	command	List PCI devices	e.g. Audio, USB, VGA	lspci | head	00:00.0 Host bridge: <br>Intel Xeon E3-1200 v6/7th Gen Core Processor <br>Host Bridge/DRAM Registers<br>00:02.0 VGA: Intel Corporation HD Graphics<br>00:14.0 USB: Intel Corporation Sunrise Point-LP	linux_01_code

lsusb	command	List USB devices	e.g. keyboard, mouse, usb drives	lsusb	Bus 002 Device 001: ID 1d6b:<br>0003 Linux Foundation 3.0 root hub	linux_01_code

modinfo	command	Info about loaded modules		modinfo e100 (ethernet)	filename:&nbsp; /lib/modules/5.15.13-200.fc35.x86_64/kernel/drivers/net/ethernet/intel/e100.ko.xz<br>firmware:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; e100/d102e_ucode.bin&nbsp;<br>license:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; GPL v2&nbsp;	linux_01_code

modprobe <module>	root command	Load a &lt;module&gt;\(^*\) temporarily	\(^*\)subdir of /lib/modules!	modprobe parport		linux_01_code

mount	command	List mounted file systems		mount	proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)	linux_01_code

rmmod <module>	root command	Remove requested &lt;module&gt; from the current kernel\(^*\)	\(^*\)if its not busy!	rmmod parport_pc		linux_01_code

passwd_timeout=<n>	/etc/sudoers	Change the "sudo five minute rule"\(^*\) to &lt;n&gt; minutes	\(^*\)once the password is entered, do as much sudos as you like for 5min	sudo /usr/bin/visudo &gt;&gt; echo "passwd_timeout=0"		linux_01_code

sudo	command	Get root permissions temporarily		sudo su	[root@eryn steven]#	linux_01_code

sudo su	commands	Open a root shell		sudo su	[root@eryn steven]#&nbsp;&nbsp;	linux_01_code

/usr/bin/visudo	root command	Edit the /etc/sudoers file		sudo visudo	#Be root user, without needing the root password.<br>root&nbsp;&nbsp;&nbsp; ALL=(ALL)&nbsp;&nbsp;&nbsp;&nbsp; ALL&nbsp;	linux_01_code

<user>&nbsp; &nbsp; ALL=(ALL)&nbsp; &nbsp; ALL	sudoers formula	Give &lt;user&gt; full root privileges\(^*\) with its user password	\(^*\)no need not the root password to gain privileges!	sudo visudo	root&nbsp; &nbsp; &nbsp; ALL=(ALL)&nbsp;&nbsp;&nbsp; ALL<br>steve&nbsp; &nbsp; ALL=(ALL)&nbsp;&nbsp;&nbsp; ALL	linux_01_code


<user>&nbsp; &nbsp; ALL=(ALL)&nbsp; &nbsp; NOPASSWD: ALL	sudoers formula	Give &lt;user&gt; full root access without any password at all		sudo visudo	root&nbsp; &nbsp; &nbsp; ALL=(ALL)&nbsp;&nbsp;&nbsp; ALL<br>steve&nbsp; &nbsp; ALL=(ALL)&nbsp; &nbsp;NOPASSWD: ALL	linux_01_code

F12 / F1	Shortcut	<div>Boot into BIOS<br></div>				linux_01_code

inst.xdriver=vesa	boot option	Use standard vesa video driver				linux_01_code

inst.resolution=1024x768	boot option	Use 1024x768 resolution				linux_01_code

inst.vnc	boot option	Run installation as VNC server				linux_01_code

inst.vncpassword=<password>	boot option	Client uses &lt;password&gt; to connect to installer\(^*\)	\(^*\)at least 8 characters!			linux_01_code

rescue	boot option	Run the kernel to open Linux rescue mode\(^*\)	\(^\)instead of installing			linux_01_code

fdisk	command	Create or manipulate partition (table)s				linux_01_code

h	top command	Get help options		h	Z,B,E,e&nbsp;&nbsp; Global: 'Z' colors; 'B' bold;<br>&nbsp; l,t,m,I&nbsp;&nbsp; Toggle: 'l' load avg; 't'	git_01_code

top	command	Real time TUI for processes		top	2576 steven 20 0 198264 S&nbsp;Anki&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <br>2915 steven 20 91176&nbsp; 67332 S QtWebEngineProc	git_01_code


gnome-disks	command	Gnome Disk Utility\(^*\)	\(^*\)manage, partition and add fs'			linux_01_code

echo "modprobe <module>" &gt;&gt; any_startup_script	/any/startup_script	Load a module permanently				linux_01_code

vmlinuz	boot option	Kompressed kernel				linux_01_code

initrd=initrd.img	boot option	Inital ram disk\(^*\)	\(^*\)modules and tools to start the installer			linux_01_code

text	boot option	Run installation in plain-text mode				linux_01_code

root:x:0:0:root:{{c1::/root}}:/bin/bash	/etc/passwd	Root home directory		cat /etc/passwd | grep "root"		Cloze

root:x:0:{{c1::0}}:root:/root:/bin/bash	/etc/passwd	Root GID		cat /etc/passwd | root		Cloze

journalctl {{c1::_SYSTEMD_UNIT}}{{c1::=}}{{c1::service}}	option and argument	Show messages for specific service		journalctl _SYSTEMD_UNIT=sshd.service	Jan 13 08:12:53 eryn sshd[867]: Server listening on 0.0.0.0 port 22. <br>Jan 13 08:12:53 eryn sshd[867]: Server listening on :: port 22.	Cloze

journalctl {{c1::-a}}	option	Show all fields\(^*\)	\(^*\)even if they include unprintable characters or are very long.	journalctl -a	Sep 07 14:33:35 fedora kernel: Linux version 5.11.12-300.fc34.x86_64 (mockbuild@bkernel01.iad2.fedoraproject.org) <br>(gcc (GCC) 11.0.1 20210324 (Red Hat 11.0.1-0), <br>GNU ld version 2.35.1-41.fc34) #1 SMP Wed Apr 7 1>&nbsp;	Cloze

journalctl {{c1::-b}} {{c1::<boot_id>}}	flag and argument	View messages from a particular boot		journalctl -b e26fd4fb29bf4160bb52dbb0b66b7bc8	Sep 07 14:33:35 fedora kernel: Linux version 5.11.12-300.fc34.x86_64&nbsp;<br>Sep 07 14:33:35 fedora kernel: Command line: <br>BOOT_IMAGE=(hd1,gpt2)/vmlinuz-5.11.12-300.fc34.x86_64 root&gt;	Cloze

journalctl {{c1::-f}}	option	Follow syslog messages as they come in		journalctl -f	Jan 24 09:38:42 eryn gnome-terminal-[124095]: <br>void terminal_screen_shell_preexec(VteTerminal*): <br>assertion '!priv->between_preexec_and_precmd' failed	Cloze

journalctl {{c1::-k}}&nbsp;	option	See only kernel messages		journalctl -k	Jan 13 08:12:48 eryn kernel: Linux version 5.15.13-200.fc35.x86_64<br>Jan 13 08:12:48 eryn kernel: Command line: <br>BOOT_IMAGE=(hd0,gpt2)/vmlinuz-5.15.13-200.fc35.x86_64 root=U> <br>Jan 13 08:12:48 eryn kernel: <br>x86/fpu: Supporting XSAVE feature 0x001: 'x87 floating point registers'&nbsp;	Cloze

journalctl {{c1::PRIORITY=0}}	argument	Show only emergency syslog messages		journalctl PRIORITY=0	-- No entries --&nbsp;	Cloze

journalctl {{c1::PRIORITY}}{{c1::=}}{{c1::<0-7>}}	option and argument	Show messages from a particular syslog log level (0-7)	e.g.: 0-7	journalctl PRIORITY=1	Nov 03 07:47:23 eryn sendmail[42944]: <br>unable to qualify my own domain name (eryn) -- using short name	Cloze

journalctl {{c1::--list-boots}}	flag	List the boot IDs for each time the system was booted		journalctly --list-boots | head	-52 e26fd4fb29bf4160bb52db 2021-09-07 14:33:35 <br>-51 92ed1188e406448797379 2021-09-07 14:42:56&nbsp;	Cloze


modinfo {{c1::-d}} {{c1::<modul>}}&nbsp;	option and argument	Get a description for a &lt;modul&gt;\(^*\)	\(^*\)most helpful if available	modinfo -d e100	Intel(R) PRO/100 Network Driver&nbsp;	Cloze

modinfo {{c1::-n}} {{c1::<module>}}	option and argument	Get the file behind a &lt;module&gt;		modinfo -e e100	/lib/modules/5.15.13-200.fc35.x86_64/kernel/drivers/net/ethernet/intel/e100.ko.xz	Cloze

modprobe {{c1::-r}} {{c1::<module>}}	option and argument&nbsp;	Remove &lt;module&gt; -- plus <i>dependencies</i> -- from the current kernel\(^*\)	\(^*\)if it's not busy!	modprobe -r parport_pc		Cloze

{{c1::systemctl}} {{c1::enable}} {{c1::--now}} {{c1::cockpit.socket}}	snippet	Enable cockpit.socket -- now!		systemctl enable --now cockpit.socket		Cloze


ln {{c1::-s}}	option	Make symbolic links&nbsp;	..instead of hard links			Cloze

who {{c1::-u}}	option	Show users logged in	steven tty2 2021-11-09 07:37 00:36 4265 (tty2)			Cloze

who {{c1::-H}}	argument	Print line of column headings	NAME&nbsp;&nbsp;&nbsp;&nbsp; LINE&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TIME&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; COMMENT			Cloze

root:x:{{c1::0}}:0:root:/root:/bin/bash&nbsp;	/etc/passwd	Root UID				Cloze


lspci {{c1::-v...v}}	flag	Get more...more verbose output	e.g. drivers			Cloze


/usr \(\rightarrow\) /usr	Assign Partition to Directory	<ol><li>{{c1::Attackers can't remove/replace system apps with corrupted versions}}<br></li><li>{{c2::Share /usr over the network (NFS, Samba)}}<br></li></ol>		Cloze		

Assign Partition to Directory	/usr \(\rightarrow\) /usr	<ol><li>{{c1::Attackers can't remove/replace system apps with corrupted versions}}<br></li><li>{{c2::Share /usr over the network (NFS, Samba)}}<br></li></ol>		Cloze		


"Bash uses untyped variables"
