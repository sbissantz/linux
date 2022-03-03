# Command reference for Linux 


## Becoming a Linux Power User


### Getting help

Information quadrega as a *general user*:

| Syntax | Description |
| ------ | ----------- |
|`type <command>`| Show me location & type of `<command>` |
|`info <command>`| Show me the info document of `<command>` |
|`man <command>`| Show me the command manual of `<command>` |
|`man -k <command>`| Search the name & summary section of all manpages for `<command>` |
| `<command> --help` | Show me the reference manual of `<command>` |

Note: if `man -k` does not give output, initialize the man page data base:

| mandb | Initialize the man page database |

Information quadrega as a *system administrator*:

| Syntax | Description |
| ------ | ----------- |
|`man 1 <command>`| Show me the user commands man page of the `<command>` (i.e., commands that can be run from shell by a regular user) |
|`man 5 <command>`| Show me the file formats & conventions man page of `<command>` (e.g., configuration files like `passwd`) |
|`man 8 <command>`| Show me	the system administration tools & daemons man page of `<command>` (i.e., commands that require root or other administrative privileges to use) |

### Using the Shell

#### Command line completion

| Syntax | Description |
| ------ | ----------- |
| `[regular char]<TAB>` | Complete with a Command, alias or function name |
| `@<TAB>` | Complete with a hostname (..from `/etc/hosts`) |
| `~<TAB>` | Complete a username (e.g., root) |
| `$<TAB>` | Complete with a shell variable |

#### list 

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
| `ls | wc -w` | Print the number of files in a directory |

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

**Examples**

| Syntax | Description |
| ------ | ----------- |
|`ls a*`| List any file that begins with `a` |
|`ls *e`| List any file that ends with `a` |
|`ls *c*`| List any file that contains `c` |
|`ls [a,b,c]*`| List any file that starts with `a,b,c` |
|`ls *[a-z]*`| List any file that contains a letter |

#### Add (files, directories & symlinks )

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

#### Copy

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

#### Move & rename

```
mv [option] [file/dir/pattern]
```

| Syntax | Description |
| ------ | ----------- |
| `mv <old_file> <new_file>` | Rename `<old_file>` to `<new_file>`|	
| | |
| `mv <file> <path>` | Copy/move file to home directory |	
| `mv <file> ~` | Rename/Move file to home directory |	

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

#### Archiving 

```
tar [option] [output_file/dir/pattern] [input_file/dir/pattern]
```

tar	command	Archive files		tar cvzf file file.tar.gz *c		linux_01_code

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

#### General user and machine info 

| Syntax | Description |
| ------ | ----------- |
| `who` | Show me who is logged in |
| `whoami` | Show me who am I (i.e., prints only the name in `who`) |
| | |
| `hostname` | Show me my computer's host name |
| | |
| `uname` |	Show me the type of system running |
| | |
| `id` | Show me user and group ID |

#### History & command line recall

| Syntax | Description |
| ------ | ----------- |
| `history` |	Show me the command history |
| | |
| `! - 2` | Run the penultimate command from history |	
| `!<n>` | Run command `<n>` from my command history |
| `!!` | Run previous command from history file |	
| `!?<string>?` |	Run command from histroy file containing `<string>` |	
| | |
| `fc <number(s)>` | Display command(s) from history; execute `<number>` afterwards |






sort {{c1::-f}}&nbsp;	option	Sort files ignoring upper an lowercase				Cloze

echo {{c1::-n}}	option	Do not output the trailing newline&nbsp;		#!/bin/bash<br>N=0<br>until [ $N -ge 3 ] ; do<br>&nbsp;&nbsp;&nbsp; echo -n $N<br>&nbsp;&nbsp;&nbsp; let N=$N+1<br>done	123	Cloze

alias {{c1::<shortcut>}}{{c1::=}}{{c1::'&lt;command(s)&gt;'}}	formula	Alias formula		alias l='ls -l'		Cloze



{{c1::export}} {{c1::<VAR>}}{{c1::=}}{{c1::&lt;value(s)&gt;}}	formula	Shell variable formula		export EDITOR=nvim ; echo $EDITOR	nvim	Cloze

\[ nonprinting chars \]	prompt character (omit space)	Include a sequence of nonprinting chars	e.g. color effects, blink			linux_01_code




<command> {{c1::&>;}} &lt;file&gt;	file-matching metacharacter	Overwrite with the output of &lt;command&gt; the content of &lt;file&gt;				Cloze

[command] {{c1::>&gt;}} [file]	file-matching metacharacter	Direct the output of [command] to [file]	append at the end			Cloze





let	command	Evaluate arithmetic expressions	No spaces!	BIGNUM=1024<br>let RESULT=$BIGNUM/16 ; echo $RESULT	64	linux_01_code

bc	command	Arbitrary precision calculator		BIGNUM=1024<br>RESULT=`echo "$BIGNUM / 16" | bc` ; <br>echo RESULT	64	linux_01_code

expr	command	Evaluate (logical/mathematical) expressions	Requires whitespaces!	BIGNUM=1024<br>RESULT=`expr $BIGNUM / 16` ; echo $RESULT	64	linux_01_code



and (ampersand)	command&nbsp;	Have the command run in the bg		troff -me&nbsp; foo | lpr &amp;		linux_01_code



mail	command	Send mail message to a local account				linux_01_code

<div><span>wc</span><br></div>	command	print newline, word, and byte counts for each file				linux_01_code


declare	command	Get a list (messy) of environmental variables	..use with '| grep'			linux_01_code

alias&nbsp;	command	Show me all aliases				linux_01_code

pwd	command	Show me my current working directory				linux_01_code





tty[x]	who -uH output	The [x]th virtual console&nbsp;	...on the monitor connected to the computer		steven&nbsp;&nbsp; tty2&nbsp; &nbsp;2021-11-09 07:37 00:43&nbsp; &nbsp;4265 (tty2)&nbsp;<br>	linux_01_code

COMMENT	who -uH	The name of the remote computer	..from which the user is logged in		NAME&nbsp; PID COMMENT <br>&nbsp; &nbsp; &nbsp; steven&nbsp; &nbsp; 5235 <u>(91.10.107.103)&nbsp;</u>	linux_01_code


set	command	Set shell options				linux_01_code

set -o vi	snippet	Set vi to edit shell command lines	..put in .bashrc for permanent change			linux_01_code


sort	command	Sort lines of text files				linux_01_code

less	command	Page through output side by side	..usefull with large files			linux_01_code

<Space>	less command	Move by page				linux_01_code

<Enter>	less command	Move by line				linux_01_code



echo	command	Print text on the screen		echo "Hello"	Hello	linux_01_code

export	command	Sets an&nbsp;<i>attribute</i> for a&nbsp;<i>shell variable</i>\(^*\)	\(^*\)<a href="https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables">https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables</a>	export EDITOR=nvim ; echo $EDITOR	nvim	linux_01_code

source&nbsp;	command	Read and execute files from current shell		echo "foo" >&gt; .bashrc ; source .bashrc		linux_01_code



su	command	<br>Open a shell as a new user	..often root (sudo)			linux_01_code

exit	command	Quit from a shell				linux_01_code




<command>&nbsp;<b>$</b>( &lt;commands&gt; )&nbsp;	command substitution	Make the output &lt;command&gt; the <i>argument</i> for other &lt;commands&gt;		vi $(find /home | grep foo)		linux_01_code







### Moving Around in the file system

&>	file-redirection metacharacter	Redirect a <commands&gt; error message <i>and</i> output to &lt;file&gt;		[command] &amp;&gt; [file]		linux_01_code

cat	command	Concetenate files to output		cat bashrc | less	# .bashrc <br> <br># Source global definitions <br>if [ -f /etc/bashrc ]; then <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; . /etc/bashrc&nbsp;	linux_01_code

cd	command	Change directory		cd /Pictures ; pwd	/home/steven/Pictures	linux_01_code

$OLDPWD	enviroment variable	The working directory before cd-ing into the current one		cd ~/projects/R/ ; echo $OLDPWD	/home/steven	linux_01_code

-&nbsp;	letter file mode bit	Turn off permission		chmod -v a-w bar/	mode of 'baz/' retained as 0555 (r-xr-xr-x)&nbsp;	linux_01_code

{{c1::chown}} {{c1::<user>}} {{c1::&lt;file&gt;}}	formula	Chown formula	Make &lt;user&gt; new owner of &lt;file&gt;	sudo chown steven baz/ ; ls -ld baz	drwxr-xr-x. 1 steven steven baz/	Cloze


chmod {{c1::-R}}	option	Change file's permission recursively		chmod -v -R 555 baz/	mode of 'baz' retained as 0555 (r-xr-xr-x)&nbsp;	Cloze


{{c1::chmod}} {{c1::<filemodebits>}} {{c1::file}}&nbsp;	formula	Chmod <i>numerical</i> filemodebits formula		chmod -v -R 555 baz/	mode of 'baz' retained as 0555 (r-xr-xr-x)&nbsp;	Cloze

{{c1::chmod}} {{c1::<ugoa>}}{{c1::&lt;+-=&gt;}}{{c1::&lt;rwxst&gt;}} {{c1::&lt;file&gt;}}	formula	Chmod&nbsp;<i>letter</i> filemodebits formula		chmod -v a+w baz/	mode of 'baz/' changed from 0555 (r-xr-xr-x) to 0777 (rwxrwxrwx)	Cloze

s	permission set	User can run but only root can execute		ls -l /bin/mount	-rwsr-xr-x.	linux_01_code

x	permission set	Executable file		ls -l ibm-touchpad.sh	-rwxrwxrwx.	linux_01_code


chown {{c1::-R}}		Change file ownership recursively		chown -R baz ; ls -l baz	drwxrwxr-x. 1 steven steven 0 sub_1/ <br>drwxrwxr-x. 1 steven steven 0 sub_2/	Cloze

chown {{c1::<user>}}{{c1:: :}}{{c1::&lt;group&gt;}} {{c1::&lt;file&gt;}}	arguments	Make &lt;user&gt; and &lt;group&gt; new owner of &lt;file&gt;		chown steven:committer crunchy_doku/ ; s -ld baz	drwxr-xr-x. 1 steven steven 0 crunchy_doku/&nbsp;	Cloze


umask&nbsp;{{c1::000}}	umask value	Full open file/dir permission		umask 000; touch foo; mkdir baz; ls -ld foo bar	drwxrwxrwx. 1 steven steven 0 Nov 19 10:02 bar/ <br>-rw-rw-rw-. 1 steven steven 0 Nov 19 10:02 foo&nbsp;	Cloze

umask {{c1::002}}	umask value	Default file/dir permission		umask 002; touch foo; mkdir baz; ls -ld foo baz	drwxrwxr-x. 1 steven steven 0 Nov 19 10:20 baz/ <br>-rw-rw-r--. 1 steven steven 0 Nov 19 10:20 foo&nbsp;	Cloze

umask {{c1::022}}	umask value	Root file/dir permission		umask 022; touch foo; mkdir baz; ls -ld foo baz	drwxr-xr-x. 1 steven steven 0 Nov 19 10:18 baz/ <br>-rw-r--r--. 1 steven steven 0 Nov 19 10:18 foo&nbsp;	Cloze


chown	command	Make ...\(^*\) new owner of <file>	\(^*\)user, group	sudo mkdir baz ; sudo chown steven ~/baz ; ls -ld baz/	drwxr-xr-x. 1 steven steven 0 baz/	linux_01_code

umask	command	Display or set default file permission		umask	2	linux_01_code

-	file mode bit	File		ls -l foo	-rw-r--r--.&nbsp;<br>	linux_01_code

d	file mode bit	Directory		ls -ld baz	drwxrwxrwx	linux_01_code


a	letter file mode bit	Permissions for all		chmod -v a-w baz/	mode of 'baz/' changed from 0774 (rwxrwxr--) to 0664 (rw-rw-r--)&nbsp;	linux_01_code

+	letter file mode bit	Turn on permission		chmod -v a+w baz/	mode of 'baz/' changed from 0555 (r-xr-xr-x) to 0777 (rwxrwxrwx)&nbsp;	linux_01_code

o	letter file mode bit	Permission for others		chmod -v o-wx baz/	mode of 'baz/' changed from 0775 (rwxrwxr-x) to 0744 (rwxr--r--)&nbsp;	linux_01_code

u	letter file mode bit	Permission for the user		chmod -v u+x baz/	mode of 'baz/' changed from 0555 (r-xr-xr-x) to 0755 (rwxr-xr-x)&nbsp;	linux_01_code

g	letter file mode bit	Permission for the (assigned) group&nbsp;		chmod -v ug+wx baz/	mode of 'baz/' changed from 0755 (rwxr-xr-x) to 0777 (rwxrwxrwx)	linux_01_code

w	permission set	Writable file		chmod + w test.txt ; ls test.txt	drwxrwxrwx	linux_01_code

0	numerical file mode bit	No permission		chmod 000 foo.txt ; sudo ls foo.txt	----------.	linux_01_code

1	numerical file mode bit	Execute permission		chmod 100 foo.txt ; ls -l foo.txt	---x------	linux_01_code

2	numerical file mode bit	Write permission		chmod 200 foo.txt ; ls -l foo.txt	---w------	linux_01_code

4	numerical file mode bit	Read permission		chmod 400 foo.txt ; ls -l foo.txt	b-r--------.	linux_01_code

chmod	command	Change a <file>'s permission set according to &lt;filemodebits&gt;	i.e., file permissions	chmod 700 .ssh/ ; ls -ld .ssh/&nbsp;	drwx------.	linux_01_code

l	file mode bit	Symbolic link			lrwxrwxrwx	linux_01_code

t	permission set	Sticky bit is set for directory	User can add items but root must delete		drwxrwxr-t	linux_01_code

r	permission set	Readable file			drwxrwxrwx	linux_01_code

2>	file-redirection metacharacter	Redirect error message		command 2&gt; /dev/null		linux_01_code


mkdir	command	Make directory		mkdir bar ; ls bar	bar/	linux_01_code




mv	command	Move and rename a file		mv -v baz/foo baz/bar	renamed 'test' -> 'testi'	linux_01_code

date	command	Show me the current date and time zone		date	Tue Feb 15 08:45:04 AM CET 2022	linux_01_code

{{c1::date}} {{c1::'+%...'}}	formula	Date formula	see: man date for formats			Cloze



;	command expansion character	Run a sequence of commands		date ; echo "hello"	Thu Nov 18 09:04:50 AM CET 2021 <br>hello&nbsp;	linux_01_code

%D	date format	Date	%m/%d/%y	date '+%D'	11/25/21	linux_01_code





'$[arithmetic - operation]'	echo command	Pass arithmetic result to a command		echo $[5-3]	2	linux_01_code

$BASH	environment variable	The full pathname of the bash command		echo $BASH	/usr/bin/bash	linux_01_code

$BASH_VERSION	environment variable	The version of the bash command		echo $BASH_VERSION	5.1.0(1)-release	linux_01_code

$HISTCMD	environment variable	The number of the current command in the history list		echo $HISTCMD	986	linux_01_code

$HISTFILE	environment variable	The location of the history file		echo $HISTFILE	/home/steven/.bash_history	linux_01_code

$HISTSIZE	environment variable	The number of history entries		echo $HITSFILESIZE	1000	linux_01_code

$HOME	environment variable	the path of the home directory		echo $HOME	/home/steven	linux_01_code

$HOSTTYPE	environment variable	The computer architecture		echo $HOSTTYPE	x86_64	linux_01_code

&nbsp;$OSTYPE	environment variable	Current OS		echo $OSTYPE	linux-gnu	linux_01_code

<div>$PATH</div>	environment variable	The current path		echo $PATH	/home/steven/.local/bin:/home/steven/bin:/usr/lib64/	linux_01_code

$PROMPT_COMMAND	environment variable	The command which runs each time before prompt is displayed		echo $PROMPT_COMMAND	history -a	linux_01_code

$PS1	environment variable	The prompt of my shell		echo $PS1	[\u@\h \W]\$&nbsp;	linux_01_code

$PWD	environment variable	The working directory		echo $PWD	/home/steven/dotelse	linux_01_code

$RANDOM	environment variable	A random number between 0 and 99999		echo $RANDOM	3872	linux_01_code

$SHELL	environment variable	The current shell	/bin/bash	echo $SHELL	/bin/bash	linux_01_code

$TMOUT	environment variable&nbsp;	The time (without receiving input) till shell goes idle (exits)	..useful to set as a security feature	echo $TMOUT	180	linux_01_code

$USER	environment variable	The user name		echo $USER	steven	linux_01_code






### Working with text files

wc {{c1::-w}}	option	Print the word count				Cloze


wc {{c1::-m}}	option	Print the char count		ls | wc -m	164	Cloze

cut	command	Remove sections of lines of files and text		grep /home /etc/passwd | cut -f6 -d':' -	/home/steven	linux_01_code





### Managing Running Processes

{{c1::r}} {{c1::<pid>}}&nbsp;{{c1::1}}&nbsp;<br>...<br>{{c2::r}} {{c2::&lt;pid&gt;}}&nbsp;{{c2::19}} #lowest	top (root)	Renice the process &lt;pid&gt; to have <i>low</i> priority				Cloze

{{c1::r}} {{c1::<pid>}}&nbsp;{{c1::-1}} <br>...<br>{{c2::r}} {{c2::&lt;pid&gt;}}&nbsp;{{c2::-20}} #highest	top (root)	Renice the process &lt;pid&gt; to have <i>high</i> priority				Cloze

{{c1::k}} {{c1::<pid>}} {{c1::15}}	top	Kill the process &lt;pid&gt; cleanly				Cloze

{{c1::k}} {{c1::<pid>}} {{c1::9}}	top command	Kill the process &lt;pid&gt; outright				Cloze

{{c1::r}} {{c1::<pid>}}&nbsp;{{c1::1}}&nbsp;<br>...<br>{{c2::r}} {{c2::&lt;pid&gt;}}&nbsp;{{c2::19}} #lowest	top (root)	Renice the process &lt;pid&gt; to have <i>low</i> priority				Cloze

{{c1::r}} {{c1::<pid>}} {{c1::0}}	top (root)	Renice the process &lt;pid&gt; to have <i>normal</i> priority				Cloze

{{c1::r}} {{c1::<pid>}}&nbsp;{{c1::-1}} <br>...<br>{{c2::r}} {{c2::&lt;pid&gt;}}&nbsp;{{c2::-20}} #highest	top (root)	Renice the process &lt;pid&gt; to have <i>high</i> priority				Cloze

nice {{c1::-n}} {{c1::<nice>}} &lt;command&gt;	option and argument	Start a process with a given &lt;nice&gt; integer value		nice -n +5 updatedb &amp;&nbsp;		Cloze

ps {{c1::-e}}	option	List every\(^*\) process on the system	\(^*\)excluding background processes	ps -e	&nbsp; &nbsp; PID TTY&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; TIME CMD <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 ?&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 00:00:01 systemd <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2 ?&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 00:00:00 kthreadd&nbsp;	Cloze

ps {{c1::-eo}} {{c1::comm}}	options and argument	Show me the name of the command for each process		ps -eo comm	xdg-dbus-proxy <br>bwrap&nbsp;	Cloze

ps {{c1::-eo}} {{c1::group}}	options and argument	Show me the group associated with every running process		ps -eo group	steven <br>root	Cloze

ps {{c1::-eo}} {{c1::pid}}	options and argument	See the pocess ID for every running process		ps -eo pid	PID <br>&nbsp; &nbsp;1 <br>&nbsp; &nbsp;2&nbsp;	Cloze

ps -eo <arguments> {{c1::--sort=-&lt;argument&gt;}}	flag and argument	Sort by the highest &lt;argument&gt; first		ps -eo pid,user,rss --sort=-rss	Anki&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; steven&nbsp;&nbsp; 539408 <br>packagekitd&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp; 509696	Cloze

ps -eo <arguments> {{c1::--sort=&lt;argument&gt;}}	flag and argument	Sort by lowest &lt;argument&gt; first		ps -eo pid,user,rss --sort=rss	root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0 kworker<br>steven&nbsp;&nbsp;&nbsp;&nbsp; 180 bwrap&nbsp;	Cloze

ps {{c1::-eo}} {{c1::rss}}	options and argument	Show me the resident memory\(^*\) used for each process	\(^*\)the memory actually used by a process	ps -eo rss	39884 <br> 1096&nbsp;	Cloze

ps {{c1::-eo}} {{c1::uid}}	argument	Show me the user ID\(^*\) for every running process	\(^*\)identifies the user to the system	ps -eo uid	&nbsp; &nbsp; 0 <br>&nbsp; 998 <br>&nbsp; 193	Cloze

ps {{c1::-eo}} {{c1::gid}}	options and argument	Show me the <i>group ID</i>\(^*\) for every running process	\(^*\)identifies the group to the system	ps -eo uid	&nbsp; 996 <br>&nbsp; 193 <br>&nbsp; &nbsp; 0	Cloze

ps {{c1::-eo}} {{c1::user}}	options and argument	Show me the user name associated with every running process		ps -eo user	root <br>colord <br>root&nbsp;	Cloze

ps {{c1::-eo}} {{c1::vsz}}	options and argument	Show me the virtual memory\(^*\) allocated to each process	\(^*\)the amount of space allocated to a process	ps -eo vsz	5302384 <br>5340172	Cloze

ps {{c1::u}}	option	List processes with user information\(^*\)	\(^*\)programs, ressources and user	ps -u	steven 31358&nbsp; 1.5&nbsp; 0.0 224616&nbsp; 0:00 bash <br>steven 31391&nbsp; 0.0&nbsp; 0.0 225564&nbsp; 03:30&nbsp;&nbsp; 0:00 ps -u&nbsp;	Cloze

ps {{c1::aux}}	options	Fully list all\(^*\) processes for <i>all</i> users on the system	\(*\)including root and background processes	ps aux | less	USER PID %CPU %MEM VSZ RSS TTY ... TIME COMMAND&nbsp;<br>steven 3995 0.1&nbsp; 0.0 224616&nbsp; 6160&nbsp;pts/1&nbsp;0:00 bash&nbsp;<br>steven 4029 0.0&nbsp; 0.0 225568&nbsp; 3660 pts/1 0:00 ps u&nbsp;	Cloze

{{c1::nice}} {{c1::-n}} {{c1::<priority>}}&nbsp;{{c1::&lt;command&gt;}}	formula	Nice formula		ps u ; nice -n +5 updatedb and ; top		Cloze

{{c1::renice}} {{c1::-n}} {{c1::<priority>}}&nbsp;{{c1::&lt;PID&gt;}}	formula	Renice formula	Alter the processes (&lt;PID&gt;) &lt;priority&gt;	ps u ;&nbsp;renice -n +5 78678 ; top		Cloze

ps {{c1::ux}}	options	Fully\(^*\) list <i>user</i> processes running on your system	\(^*\)all infos and including background processes	ps ux | less	USER PID %CPU %MEM VSZ RSS TTY ... TIME COMMAND <br>steven 3995 0.1&nbsp; 0.0 224616&nbsp; 6160&nbsp;pts/1&nbsp;0:00 bash <br>steven 4029 0.0&nbsp; 0.0 225568&nbsp; 3660 pts/1 0:00 ps u 	Cloze



{{c1::kill}} {{c1::<signal>}} {{c1::&lt;pid&gt;}}	kill formula	Kill formula		kill -SIGHUP 104321	[1]&nbsp; + hangup &nbsp; &nbsp; nvim	Cloze

{{c1::killall}} {{c1::<signal>}} {{c1::&lt;name&gt;}}	formula	Killall formula		killall nvim	[2]&nbsp; + terminated&nbsp; nvim	Cloze


PID	ps u	Process Identifier\(^*\)	\(^*\)unique			linux_01_code

fg {{c1::%?<pattern>}}<br>bg {{c1::%?&lt;pattern&gt;}}	argument	Bring command including &lt;pattern&gt; back to fg\(^*\) / run in bg	\(^*\)string must be unambiguous!	bg %?im	nvim	Cloze

fg {{c1::%<n>}}<br>bg {{c1::%&lt;n&gt;}}	argument	Bring job &lt;n&gt; back to the / run in bg		bg %1	nvim	Cloze

fg {{c1::%--}}<div><span style="color: var(--field-fg); background: var(--field-bg);">bg {{c1::%--}}</span></div>	argument	Bring the penultimate&nbsp;command back to fg / run in bg		fg %--	nvim	Cloze

fg {{c1::%<command>}}<br>bg {{c1::%&lt;command&gt;}}	argument	Bring &lt;command&gt; back to fg / run in bg		fg nvim	nvim	Cloze


M	top command&nbsp;	Sort by memory usage\(^*\)	\(^*\)instead uf cpu			git_01_code

P	top command	Sort by CPU\(^*\)	\(^*\)instead of memory			git_01_code

R	top command	Reverse sort your output				git_01_code

u <user>	top command	Show only&nbsp; &lt;user&gt;s processes				git_01_code

r <pid>	top command	Renice a process\(^*\)	\(^*\).e.: give it less priority to the processor			git_01_code

k <pid>	top command	Kill process with &lt;pid&gt;				git_01_code

gnome-system-monitor	command	GUI for processes, ressources and fs				git_01_code

Ctrl + S	gnome-system-monitor shortcut	Stop\(^*\) the process	\(^*\)I.e.: pause			git_01_code

Ctrl + C	gnome-system-monitor shortcut	Continue the process				git_01_code

Ctr + E	gnome-system-monitor shortcut	End the process\(^*\)	\(^*\)terminate cleanly (15)			git_01_code

Ctrl + K	gnome-system-monitor shortcut	Kill a process\(^*\)	\(^*\)terminate outright (9)			git_01_code


ps	command	List current processes		ps	31265 pts/0&nbsp;&nbsp;&nbsp; 00:00:00 bash <br>31297 pts/0&nbsp;&nbsp;&nbsp; 00:00:00 ps	linux_01_code

+ (STAT)	ps u	Process running in the foreground		ps u	steven&nbsp;&nbsp;&nbsp;&nbsp; 32777&nbsp; pts/0&nbsp; &nbsp;Ss&nbsp;&nbsp; 03:35&nbsp;&nbsp; 0:00 bash <br>steven&nbsp;&nbsp;&nbsp;&nbsp; 32812&nbsp; pts/0&nbsp; &nbsp;R+&nbsp;&nbsp; 03:35&nbsp;&nbsp; 0:00 ps u&nbsp;	linux_01_code

RSS	ps u	Resident Set Size	"Used size of the program in memory!"	ps u	&nbsp; &nbsp; USER&nbsp; &nbsp; PID&nbsp; &nbsp;VSZ&nbsp;&nbsp; RSS&nbsp; &nbsp;&nbsp;<br>steven 1605 374124 5768&nbsp;	linux_01_code

TIME	ps u	Cumulative System time used		ps u	USER&nbsp; &nbsp;PID TIME COMMAND <br>steven&nbsp; 1605&nbsp; 0.0&nbsp; 0.0&nbsp; /usr/libexec/&nbsp;	linux_01_code

renice	command	Alter the processes' (<PID>) &lt;priority&gt;		renice -n -5 20284 ; top	94711 steven <u>15</u>&nbsp; &nbsp;0&nbsp; 225964 top	linux_01_code

fg	command	Run a process in the foreground		fg	nvim	linux_01_code

bg	command	Run a process in the background		bg	[1]+ nvim and <br>[1]+&nbsp; Stopped&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; nvim&nbsp;	linux_01_code

SIGCONT(19)	signal	Continue after stop		<div>kill -19 18666</div>		linux_01_code

jobs	command	Check which processes run in the background		jobs	[1]+&nbsp; Stopped&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; nvim <br>[2]-&nbsp; Done&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; sudo find /usr -print > /tmp/allusrfiles&nbsp;	linux_01_code

SIGHUP (1)	signal	Reread a processes config file		kill -1 1833	<div>[1]&nbsp; + hangup &nbsp; &nbsp; nvim</div>	linux_01_code

SIGTERM (15)	signal	Terminate a process cleanly		kill -15 10432	<div>[1]&nbsp; + terminated&nbsp; nvim</div>	linux_01_code

SIGSTOP (17)	signal	Stop the process		kill -17 18764		linux_01_code

SIGKILL (9)	signal	Kill a process immediately		kill -9 1432	<div>[1]&nbsp; + killed &nbsp; &nbsp; nvim&nbsp;</div>	linux_01_code

kill	command	Signal\(^*\) a proccess by PID	\(^*\)SIGHUP(1), SIGKILL(9), SIGTERM(15), SIGSTOP(19)	kill -SIGHUP 104321	[1]&nbsp; + hangup &nbsp; &nbsp; nvim	linux_01_code

killall	command, argumnts	<signal>\(^*\) a process by &lt;name&gt;	\(^*\)SIGHUP(1), SIGKILL(9), SIGTERM(15), SIGSTOP(19)	killall nvim	<div>[2]&nbsp; + terminated&nbsp; nvim<br></div>	linux_01_code

cgroups	advanced concept	Tool to limit resource\(^*\) usage by selected pocesses	\(^*\)I.e.: cpu assignment (cpuset), processor schedueling (cpi)	man cgroups		linux_01_code

nice	command&nbsp;	Start a process (<command>) with a given &lt;priority&gt;\(^*\)	\(^*\)I.e: nice value	nice -n +5 updatedb and	<div>[3] 18911</div>	linux_01_code

### Writing simple shell scripts


Execute a shell script	2 ways to launch a shell script	<ol><li>{{c1::bash <script>}}</li><li>{{c2::#!/bin/bash}}</li></ol>		Cloze		

Execute a shell script	2 ways to launch a shell script	<ol><li>{{c1::bash <script>}}</li><li>{{c2::#!/bin/bash}}</li></ol>		Cloze		

Untyped variables	"Bash uses untyped variables"	1. {{c1::Variable are strings}}<br>2. ..{{c2::unless you 'declare' it otherwise}}		Cloze		

"Bash uses untyped variables"	Untyped variables	1. {{c1::Variable are strings}}<br>2. ..{{c2::unless you 'declare' it otherwise}}		Cloze		

\ (backslash)	shell scripting	Interpret one char literally		TODAY=$(date '+%D') ; echo "\$HOME" $TODAY&nbsp;	$HOME 12/24/21	linux_01_code

`#`	shell scripting	comment		#!/bin/bash<br># Start the programm		linux_01_code

read <variable(s)>	bash command	Read command-line input and store it in &lt;variable(s)&gt;		#!/bin/bash<br><u>read&nbsp;WORD</u><br>echo "$WORD, $WORD!"<br>$ ~/myfile	bye <br>bye, bye!	linux_01_code


if [ cond ] ; then<br>&nbsp; &nbsp;expr1<br>else<br>{{c1::elif [ cond ] ; then}}<br>&nbsp; expr2<br>else<br>&nbsp; expr3<br>fi	conditional execution	else..if statement	Spaces are mandatory!	filename="$HOME"<br>if [ -f "$filename" ] ; then<br>echo "$filename" is a regular file<br>elif [ -d "$filename" ] ; then<br>echo "$filename is a directory"<br>else<br>echo "idk what $filename is"<br>fi&nbsp;	/home/steven is a directory	Cloze

[ {{c1::!}} {{c1::cond}} ]	test expression operator	Not [cond]!		if [ ! -e "$TODOLIST" ] ; then <br>&nbsp;&nbsp;&nbsp; touch ~/.todolist&nbsp;<br>&nbsp; &nbsp; echo "touched todolist"<br>fi	touched todolist	Cloze
{{c1::[ cond ]}} {{c1::and&amp;}} {{c1::<action>}}	test expression operator	If [cond]=TRUE then &lt;action&gt;		#!/bin/bash<br>[ $# -ge 3 ] &amp;&amp; echo "There are &gt;=3 cmd-line args"&nbsp;<br>$ ./myscript test test test	There are &gt;=3 cmd-line args	Cloze

read {{c1::-p}} {{c1::"prompt msg"}} {{c1::<variable(s)>}}	argument	Prompt for infos, read and store them in &lt;variable(s)&gt;		#!/bin/bash<br><u>read -p </u>"Enter: name &amp; adjective " <u>NAME ADJ</u><br>echo "$NAME is $ADJ"<br>$ ~/myscript <br>Enter a name and an adjective Bart hair	Bart is hairy&nbsp;	Cloze

{{c1::case}} {{c1::VAR}} {{c1::in}}<br>{{c1::Result1)}}<br>{{c1:: body }} {{c1::;;}}<br>{{c1::Result2)}}<br>{{c1:: body }} {{c1::;;}}<br>{{c1::*)}}<br>{{c1:: body }} {{c1::;;}}<br>{{c1::esac}}	command	Nested if..then..else\(^*\)	\(^*\) case command = switch command	#!/bin/bash<br>case `date +%a` in<br>&nbsp;&nbsp;&nbsp; "Mon")<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo "It's monday!" ;;<br>&nbsp;&nbsp;&nbsp; "Tue" | "Wed")<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo "It's tuesday or Wednesday!" ;;<br>&nbsp;&nbsp;&nbsp; *)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo "blubb" ;;<br>esac	It's tuesday or Wednesday!	Cloze

{{c1::[ cond ]}} {{c1::and&amp;}} {{c1::<action>}} {{c1::||}} {{c1::&lt;action&gt;}}	test expression operator	Alternative one-line if...then...else		#!/bin/bash<br>dirname = /home/steven/baz<br>[ -e $dirname ] &amp;&amp; echo "$dirname exists!" || mkdir $dirname&nbsp;	/home/steven/baz exists! 	Cloze

{{c1::[ cond ]}} {{c1::||}} {{c1::<action>}}	test expression operator	If [cond]=FALSE then &lt;action&gt;		#!/bin/bash<br>dirname="/home/steven/baz"<br>[ -d "$dirname" ] || mkdir&nbsp; "$dirname"	/home/steven/baz	Cloze

[ {{c1::-n}}&nbsp;{{c1::string}} ]	tets expression operator	Is the length of <string> &gt;0 bytes?&nbsp;		#!/bin/bash<br>FILE="~/foo.txt"<br>if [ -n "$FILE" ] ; then<br>echo "$FILE is greater than 0 bytes"<br>fi	~/foo.txt is greater than 0 bytes&nbsp;	Cloze

{{c1::for}} {{c1::VAR}} {{c1::in}} {{c1::LIST}}<br>{{c1::do}}<br>&nbsp; &nbsp; &nbsp;{{c1::body}}<br>{{c1::done}}	loop	for...do...loop		#!/bin/bash<br>for NUMBER in 0 1 2 3<br>do<br>&nbsp;&nbsp;&nbsp; let RESULT=$RANDOM+$NUMBER<br>&nbsp;&nbsp;&nbsp; echo $RESULT<br>done	22483 <br>16128 <br>27922 <br>10390	Cloze

{{c1::until}} {{c1::[ cond ]}}<br>{{c1::do}}<br>&nbsp; &nbsp; {{c1::&nbsp;body}}<br>{{c1::done}}	loop	until...do...\(^*\)	\(^*\)until TRUE...do ; if TRUE stop!	#!/bin/bash<br>N=0<br>until [ $N -ge 10 ] ; do<br>&nbsp;&nbsp;&nbsp; echo -n $N<br>&nbsp;&nbsp;&nbsp; let N=$N+1<br>done	123456789	Cloze

{{c1::while}} {{c1::[ cond ]}}<br>{{c1::do}}<br>&nbsp; &nbsp; &nbsp;{{c1::body}}<br>{{c1::done}}	loop	while...do...\(^*\)	\(^*\) while TRUE do... ; if FALSE stop	#!/bin/bash<br>N=0<br>while [ $N -lt 10 ] ; do<br>&nbsp;&nbsp;&nbsp; echo -n $N<br>&nbsp;&nbsp;&nbsp; let N=$N+1<br>done	123456789	Cloze


$@	shell parameter	All arguments entered at the command line		#!/bin/bash<br>echo "all arguments are: $@"<br>$ ~/myscript foo bar	all arguments are: foo bar&nbsp;	linux_01_code

$#	shell positional parameters	Get the n° paramaters your script was given		#!/bin/bash<br>echo "My script was given $# parameters"<br>$&nbsp;~/myscript foo bar	My script was given 2 parameters	linux_01_code

$0	shell parameter	The name used to invoke your script		#!/bin/bash<br>echo "the command is called '$0'"<br>$ ~/ myscript foo	the command is called '/home/steven/myscript'	linux_01_code

$?	shell parameter	The exit status of the last command		#!/bin/bash<br>echo "The exit status is: $?" <br>if [ $? -eq 0 ] ; then <br>&nbsp;&nbsp;&nbsp; echo "Script ran successfully!" <br>fi<br>$ ~/myscript	The exit status is: 0 <br>Script ran successfully!	linux_01_code

$<n>	shell positional parameters	Match the &lt;n\(^{th}\)&gt; command-line argument		#!/bin/bash<br>echo "the first argument is $1"<br>$ ~/ myscript foo	the first argument is foo,	linux_01_code

${VAR}	shell scripting	The longform of $VAR		#!/bin/bash<br>read -p "Enter a word! " WORD <br>echo "<u>$WORD = ${WORD}</u>"	Enter a word! foo&nbsp;<br>foo = foo&nbsp;	linux_01_code

' (single quote)	shell scripting	Interpret a set of characters literally		echo '$HOME * date +D'	'$HOME * `date +D`'	linux_01_code

` (backtick)	shell scripting	Run <command> only when varibale is set\(^*\)	\(^*\)not each time the variable is read (efficiency!)	echo "$HOME * `date`"		linux_01_code

${var:-value}	bash parameter expansion	If <var> is empty or unset, expand it to &lt;value&gt;		FOO="Example" ; FOO=${FOO:-"Not Set"} ; echo $FOO	Example	linux_01_code

${var##pattern}	bash parameter expansion	Chop\(^*\) the <i>longest</i> match for <pattern> from the <i>front</i> of &lt;var&gt;s value	\(^*\)abhacken	MYFILE=/home/steven/foo.txt&nbsp;<br>FILE=${MYFILE##*/} ; echo $FILE	foo.txt	linux_01_code

${var%pattern}	bash parameter expansion	Chop\(^*\) the&nbsp;<i>shortest</i>&nbsp;match for <pattern> from the&nbsp;<i>end</i>&nbsp;of &lt;var&gt;s value	\(^*\)abhacken	MYPATH=/home/steven/foo.txt<br>DIR=${MYPATH%/*} ; echo $DIR	/home/steven	linux_01_code

${var#pattern}	bash parameter expansion	Chop\(^*\) the&nbsp;<i>shortest</i>&nbsp;match for <pattern> from the&nbsp;<i>front</i>&nbsp;of &lt;var&gt;s value	\(^*\)abhacken	MYPATH=/home/steven/foo.txt<br>EXTENSION=${MYPATH#*.} ; echo $EXTENSION	txt	linux_01_code

${var%%pattern}	bash parameter expansion	Chop\(^*\) the&nbsp;<i>longest</i>&nbsp;match for <pattern> from the&nbsp;<i>end</i>&nbsp;of &lt;var&gt;s value	\(^*\)abhacken	MYPATH=home/steven/foo.txt<br>MYHOME=${MYPATH%%/*} ; echo $MYHOME	home	linux_01_code

<sting> = <string>;	test expression operator	Are both strings equal?		STRING="friday"<br>if [ "$STRING" = "friday" ] ; then<br>echo "Yippie, it's friday!"&nbsp;<br>fi	Yippie, it's friday!&nbsp;	linux_01_code

NAME=value	shell scripting	Assign variable <NAME> a &lt;value&gt;\(^*\)	\(^*\)no spaces!	TODAY=$(date)<br>echo $TODAY		linux_01_code

$((--I))	shell script arithmetic	Incrementally decrease <I> by 1		I=0 ; echo "I - 1 = $((--I))"&nbsp;	I - 1 = 0	linux_01_code

$((I++))	shell script arithmetic	Incrementally increase <I> by 1		I=0 ; echo "I + 1 = $((++I))"	I + 1 = 1	linux_01_code

bash {{c1::-x}} <script>	option	Display each command executed\(^*\)	\(^*\)set near beginning of the script	bash -x test	+ echo hello <br>hello	Cloze

{{c1::if}} {{c1::[ cond ]}} {{c1::;}} {{c1::then}}<br>&nbsp; &nbsp;{{c1::expr}}<br>{{c1::fi}}	conditional execution	If...then statement	Spaces are mandatory!	MYVAR=1<br>if [ $MYVAR -eq 1 ] ; then<br>&nbsp; &nbsp;echo "MYVAR is set to 1"<br>fi	MYVAR is set to 1&nbsp;	Cloze

if [ cond ] ; then<br>&nbsp; &nbsp;expr1<br>{{c1::else}}<br>&nbsp; &nbsp;expr2<br>fi	conditional execution	If...then...else statement	Spaces are mandatory!	MYVAR=2<br>if [ $MYVAR = 1 ] ; then<br>&nbsp; &nbsp;echo "MYVAR = 1"<br>else<br>&nbsp; &nbsp;echo "MYVAR != 1"<br>fi	MYVAR != 1	Cloze






## Search & Find 

b	file size character	Bytes		find $HOME -size -2b	/home/steven/dead.letter <br>/home/steven/.profile&nbsp;	linux_01_code

k	file size character	Kilobytes		find $HOME -size -2kb	/home/steven/.gitconfig <br>/home/steven/.lesshst&nbsp;	linux_01_code

G	file size character	Giga Byte		sudo find -size +2G	./Videos/Climber Kit MASTER.mp4&nbsp;	linux_01_code

M	file size character	Megabyte		sudo find -size +2M	./Videos/Climber Kit MASTER.mp4&nbsp;	linux_01_code

find	command	Find user-readable files/dirs\(^*\) live&nbsp;	\(^*\)below that poing in the fs	find bash*	.bash_history <br>.bash_logout <br>.bash_profile <br>.bashrc&nbsp;	linux_01_code

tr&nbsp;	command	Translate or delete characters		for file in * ; do<br>f=`echo $file | tr [:blank:] [_]`<br>[ "$file" = "$f" ] || mv -i -- "$file" "$f"<br>done	renamed 'hdjh hjkdhas' -> 'hdjh_hjkdhas'	linux_01_code


grep	command	Within ...\(^*\), show me all&nbsp;lines&nbsp;that match the [patterns]	\(^*\)a file, text, standard output	grep alias ~/.bash_aliases	<font color="#a40000">alias</font> rm='rm -iv' <br><font color="#a40000">alias</font> rmdir='rmdir -v'&nbsp;	linux_01_code

help test	command	Get help with <i>test expression operators</i>		help test	File operators: <br>&nbsp;-a FILE&nbsp; &nbsp;True if file exists. <br>&nbsp;-b FILE&nbsp; &nbsp;True if file is block special. <br>&nbsp;-c FILE&nbsp; &nbsp;True if file is character special.	linux_01_code


sudo find	root command	Find <i>all</i> files/dirs\(^*\) live&nbsp;	\(^*\)below that point in the fs	sudo mkdir baz ; sudo find baz	baz	linux_01_code

locate	command	Search for a string in the mlocate database		locate .bashrc	/etc/skel/.bashrc	linux_01_code

updatedb	root command	Update the database for locate\(^*\)	\(^*\)runs once every day automatically			linux_01_code


ls	command	List the files/dirs in currrent directory		ls	limbing/&nbsp;&nbsp;&nbsp; Documents/&nbsp; gnu.png*&nbsp; Pictures/&nbsp; Rlibs/&nbsp;&nbsp;&nbsp; studies/	linux_01_code

./	ls -a output	Current directory		ls -a	./&nbsp; ../&nbsp; R/&nbsp; stats/&nbsp; testtheory/&nbsp; vim/&nbsp;	linux_01_code

/etc/skel	system directory	Global configs copied to any <i>new</i> user's <i>/home/user</i>\(^*\)	\(^*\)i.e.: when he/she is added to the system	ls -a /etc/skel	.bash_logout&nbsp; .bash_profile&nbsp; .bashrc	linux_01_code

../	ls -a output	Parent directory		ls -a projects	./&nbsp; ../&nbsp; R/&nbsp; stats/&nbsp; testtheory/&nbsp; vim/	linux_01_code

total	ls -l output	The total amount of diskspace in the ls-list		ls -l	total 96 <br>drwxrwxrwx. 1 steven steven climbing/&nbsp;<br>	linux_01_code


find {{c1::-size}} {{c1::+<size>}}	action and argument	Find files above &lt;size&gt;		find -size +5G	./Videos/Climber Kit MASTER.mp4&nbsp;	Cloze

find {{c1::-type}} {{c1::f}} {{c1::-perm}} {{c1::/002}}	actions and arguments	Find every <file> that is writeable for &lt;others&gt;\(^*\)	\(^*\)regardless of how the other are set	find -type f -perm /002	./projects/stanmisc/rethinking/.basr <br>./projects/stanmisc/rethinking/ch_10.R	Cloze

find <path> {{c1::-cmin}} {{c1::&lt;(+/-)time&gt;}}	action and argument	Find files by minutes of change		find . -cmin -1	./.local/state/wireplumber/restore-stream&nbsp;	Cloze

find <path> {{c1::-mmin}} {{c1::&lt;(+/-)time&gt;}}	action and argument	Find files by minutes of metadata access		find . -mmin -1	./.bash_history	Cloze

find <path> {{c1::-perm}} {{c1::-&lt;filemodebit&gt;}}	action and arguments	Find files that match <i>all</i> &lt;perm&gt;issions	\(^*\)user AND group AND others	find . -perm -222 -type d -ls	./test_2&nbsp;	Cloze

find <path> {{c1::-perm /&lt;filemodebit&gt;}}	action and argument	Find files that match <i>any</i> &lt;perm&gt;ission\(^*\)	\(^*\)user OR group OR others	find . -perm /664&nbsp;	./test_2<br>./test_3	Cloze

find <path> {{c1::-type}} {{c1::d}}	action and argument	Find only directories		find . -type d	/home/steven/./baz&nbsp;	Cloze

find <path> {{c1::-iname}} {{&lt;pattern&gt;}}	action and argument	Find a <i>case insensitive</i> &lt;pattern&gt; below &lt;path&gt;		find /etc -iname *pass*	find: ‘/etc/grub.d’: Permission denied&nbsp;	Cloze

find <path> {{c1::-name}} {{c1::&lt;pattern&gt;}}	action and argument	Find a case <i>sensitive</i> &lt;pattern&gt; below &lt;path&gt;		find /etc -name passwd	find: ‘/etc/audit’: Permission denied&nbsp;	Cloze

find <path> {{c1::-perm}} {{c1::&lt;filemodebit&gt;}}	action and argument	Find files that match the &lt;perm&gt;ission set as a whole		find /usr/bin -perm 755 -ls	714878&nbsp; -rwxr-xr-x root 29 17:59 /usr/bin/nmcli&nbsp;	Cloze

find <path> {{c1::-not}} -user/-group &lt;user/group&gt;	action	Find all files that are <i>not</i>&nbsp;owned by user/group		find /var/spool -not -user root -ls	drwx------ /var/spool/abrt-upload&nbsp;	Cloze

find <path> {{c1::-amin}} {{c1::&lt;(+/-)time&gt;}}	action and argument	Find files by minutes of access		find $HOME -cmin -1	/home/steven/.local/share/gnome-shell&nbsp;	Cloze

find <path> {{c1::-ctime}} {{c1::&lt;(+/-)time&gt;}}	action and argument	Find files by day of change		find $HOME -ctime -3	/home/steven/baz/test_1	Cloze

find {{c1::-group}} {{<group>}}	action and argument	Find files by &lt;group&gt;		find $HOME -group steven	/home/steven/.bash_profile <br>/home/steven/.bash_aliases&nbsp;	Cloze

find {{c1::-size}} {{c1::-<size>}}	action and argument	Find files <i>below</i> &lt;size&gt;		find $HOME -size -1M	/home/steven/Rlibs/4.1/StanHeaders/libs	Cloze

find files {{c1::-user}} {{c1::<user>}}	action and argument	Find files by &lt;user&gt;\(^*\)	\(^*\)I.e.: the owner	find $HOME -user steven	/home/steven/.lesshst <br>/home/steven/.bash_history	Cloze

find [options] {{c1::-exec}} {{c1::command}} {{c1:: {} }} {{c1:: \;}}	action and argument	Execute <command> on each file found		find $HOME -user steven -and -size +1G -exec echo "I found " {} \;	I found&nbsp; /home/steven/Videos/taichi/lesson1.mp4	Cloze

find <path> -user &lt;user&gt; {{c1::-and}} -size &lt;size&gt;	action	Find all files that are owned by &lt;user&gt; <i>and</i> has &lt;size&gt;		find $HOME -user steven -and -size +1G&nbsp;	/home/steven/Videos/taichi/lesson1.mp4	Cloze

find <path> {{c1::\(}} -user &lt;user&gt; {{c1::-or}} -group &lt;group&gt; {{c1::\ )}}	actions	Find all files that are owned by &lt;user&gt; <i>or</i> &lt;group&gt;		find $HOME \( -user steven -or -group steven \) -ls	...<br>/home/steven/.lesshst <br>/home/steven/.bash_history&nbsp;	Cloze

find <path> {{c1::-atime}} {{c1::&lt;(+/-)time&gt;}}	action and argument	Find files by day of access		find baz -atime -3	baz/ <br>baz/test_1	Cloze

find <point>&nbsp;{{c1::-ls}}	action	Find and list long\(^*\)	\(^*\)find with permission set	find baz -ls	321224&nbsp; 0 drwxr-xr-x 1 root baz&nbsp;	Cloze

find <path> {{c1::-mtime}} {{c1::&lt;(+/-)time&gt;}}	action and argument	Find files by day of metadata access		find baz -mtime -1	./.var/app/net.ankiweb.Anki/cache/tmp/mpv.st47dflo	Cloze

find <path> {{c1::-type f}}	action and argument	Find only files		find baz -type f	baz/test_1&nbsp;	Cloze

find baz [options] {{c1::-ok}} {{c1::command}} {{c1::{} }} {{c1::\;}}	action and argument	Execute <command> on each file found\(^*\)	\(^*\)query if its okay	find baz -type f -ok rm {} \;&nbsp;	&lt; rm ... baz/test_1 &gt; ? y <br>&lt; rm ... baz/test_2 &gt; ? y&nbsp;	Cloze

{{c1::grep}} {{c1::-i}} "[pattern]" <file>	comman and option	Within &lt;file&gt;, <i>case-insensitively</i> show me all&nbsp;lines&nbsp;that match the [patterns]		grep -i "desktop" /etc/services	sco-dtmgr&nbsp; 617/tcp&nbsp; #<u>Desktop</u> Administration Server <br>sco-dtmgr&nbsp; 617/udp #<u>Desktop</u> Administration Server	Cloze

grep {{c1::--color}} "[patterns]" <file>	flag	Within &lt;file&gt;, show me all lines that match the "[pattern]"&nbsp;<i>in color</i>		grep -ri --color root /etc/sysconfig	/etc/sysconfig/kdump:# <font color="#a40000">root</font>	Cloze

{{c1::grep}} {{c1::-r}} "[patterns]" <dir>	command, option and argument	Within &lt;dir&gt;\(^*\), <i>recursively</i>&nbsp;find me all lines that match the [patterns]	\(^*\)and all it's files	grep -ri peerdns /usr/share/doc/	/usr/share/do/setup.html ...option "usepeerdns"<br>/usr/share/doc/NEWS.md&nbsp;"PPPOPTIONS=usepeerdns"	Cloze

{{c1::grep}} {{c1::-rl}} "[pattern]" <dir>	option&nbsp;	Within &lt;dir&gt;, find me all&nbsp;<i>files</i>\(^*\)&nbsp;where the lines match the [pattern]	\(^*\)suppressing the search pattern	grep -rl "dagitty" /stanmisc/rethinking	projects/stanmisc/rethinking/ch_11.R <br>projects/stanmisc/rethinking/ch_05.R <br>projects/stanmisc/rethinking/counterfactual_plot.R 	Cloze

{{c1::grep}} {{c1::-v}} "[patterns]" <file>	option	Within &lt;file&gt;\(^*\), show me all&nbsp;lines&nbsp;that <i>don't</i> match the [patterns]		grep -vi desktop /etc/services	prosharevideo&nbsp;&nbsp; 5714/tcp&nbsp; # proshare conf video <br>prosharevideo&nbsp;&nbsp; 5714/udp # proshare conf video&nbsp;	Cloze

cut {{c1::-f<n>}} {{c1::-d'&lt;symbol&gt;'}} {{c1::-}}	arguments	Cut the &lt;n\(^{th}\)&gt; field delimited by &lt;symbol&gt;\(^*\)	\(^*\)reading from standard output	grep /home /etc/passwd | cut -f6 -d':' -	/home/steven	Cloze

{{c1::grep}} {{c1::"[patterns]"}} {{c1::<file>}}	formula	Grep formula		grep desktop /etc/services	desktop-dna&nbsp;&nbsp;&nbsp;&nbsp; 2763/tcp&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; # Desktop DNA <br>desktop-dna&nbsp;&nbsp;&nbsp;&nbsp; 2763/udp&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; # Desktop DNA&nbsp;	Cloze

[command] {{c1::| grep "[pattern]"}}	options	Find the lines that match a "[pattern]" in <i>standard</i> <i>output</i>		cat .bash_aliases | grep --color grep	alias <font color="#a40000">grep</font>='<font color="#a40000">grep</font> --color=auto'	Cloze

locate {{c1::-i}} {{c1::<file>}}	option and argument	Locate &lt;file&gt; ignoring case distinctions		locate -i dir_color	/etc/DIR_COLORS <br>/etc/DIR_COLORS.lightbgcolor&nbsp;	Cloze

find {{c1::-size}} {{c1::+<size1>}} {{c1::-size}} {{c1::-&lt;size2&gt;}}	action and arguments	Find files <i>between</i> &lt;size1&gt; &amp; &lt;size2&gt;		sudo find -size +500M -size +2G&nbsp;	./Videos/Climber Kit MASTER.mp4&nbsp;	Cloze

## shortcuts

Ctrl + Alt + Tab	Shortcut	<div>Select different views<br></div>				linux_01_code

Ctrl + D	shortcut	Quit from shell				linux_01_code

Ctrl + Alt + F[1-6]	Shortcut	Switch between virtual consoles [1-6]				linux_01_code

Ctrl + Z	shell shortcut	Stop an active program			[1]+&nbsp; Stopped&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; nvim&nbsp;	linux_01_code

Ctrl + L	shell shortcut&nbsp;	Clear the screen\(^*\)	\(^*\)useful when bg processes generate output			linux_01_code




--------------------------------------------------------------------------------








## directories & files

{{c1::httpd}} {{c1::-t}}	command and option	Check the sanity of Apache config\(^*\)	\(^*\)before the web server is started			Cloze

testparm	command	Check the sanity of samba.conf				linux_01_code

/etc/cron*	system directories	Place, where services and applications generally add cron job files	\(^*\)<b>cron.d/</b> cron.daily cron.weekly cron.montly			linux_01_code

/etc/crontab	system file	Set time for running automated tasks and varibles\(^*\)	\(^*\)associated with the cron facility			linux_01_code

/etc/exports	system file	Lists local directories which can be shared via NFS				linux_01_code

/etc/xinetd.conf	system file	Configures xinetd				linux_01_code

/etc/X11/xorg.conf	system file	Makes your computer usable with X				linux_01_code

/var/log/boot.log	system file	Boot messages gathered by rsyslogd\(^*\)	\(^*\)replaced by systemd			linux_01_code

/var/log/messages	system file	General system infos gathered by rsyslogd\(^*\)	\(^*\)replaced by systemd			linux_01_code

/var/log/secure	system file	Security related messages gathered by rsyslogd				linux_01_code

run/media/<user>	dynamic system directory	Mountpoint for USB devices	\(^*\)instead of /mnt			linux_01_code

/var/ftp	sytem directory	FTP directory				linux_01_code

/var/www	system directory	Web server directory				linux_01_code

/var	system directory (II)	Variable data files	e.g. administrative and logging data, spool directories &amp; files,			linux_01_code

/mnt	system directory (II)	Mount point for temporarily mounted filesystems				linux_01_code

/opt	system directory (II)	Add-on application software packages\(^*\)	\(^*\)3rd-party			linux_01_code

/media	system directory (II)	Mount point for removeable media				linux_01_code

/srv	system directory (II)	<i>Data</i> for system services				linux_01_code

/tmp	system directory (II)	Temporary files	\(^*\)lock files and temporry data storage			linux_01_code

/root	system directory (II)	Home directory for the root user				linux_01_code

/etc/default/grub	system file (III)	Configures <i>update-grub</i>\(^*\)&nbsp;	\(^*\)for generating&nbsp;<em>/boot/grub/grub.cfg</em>			linux_01_code


/bin	system directory (II)	Essential user command binaries\(^*\)	\(^*\)I.e.: Commands for the system admin&nbsp;<i>and</i>&nbsp;non-privileged users (e.g.; bash, csh, cp, mv, rm, cat, ls). That's why in contrast to /usr/bin, the binaries in this directory are essential.	<a href="https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch03s04.html">https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch03s04.html</a>		linux_01_code

/boot	system directory (II)	Static bootloader files	(e.g. Linux kernel, initrd)	<a href="https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch03s05.html">https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch03s05.html</a>		linux_01_code

/etc/profile	system file	(System-wide) commands the log-in shell executes	Execute: @1st login<br>Overwritten: by ~/.profile<br><br>Use: location of mailbox, size of history files (i.e., system-wide environment variables)&nbsp;and startup programs	<a href="https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables">https://gnu.org/software/bash/manual/bash.html#Shell-Variables</a>		linux_01_code

~/.bash_profile	system file	(User) commands the log-in shell executes	Execute: @1st log-in<br>Use: enviornment variables	<a href="https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables">https://gnu.org/software/bash/manual/bash.html#Shell-Variables</a>		linux_01_code


/etc/fstab	system file	Decides where to mount all partitions available to the system		cat /etc/fstab	/dev/nvme0n1p3 / btrfs&nbsp;&nbsp; subvol=root,compress=zstd:1 0 0	linux_01_code

/etc/hostname	system file	Sets the hostname for the machine		cat /etc/hostname	eryn	linux_01_code

/etc/hosts	system file	Maps IP addresses to their hostnames\(^*\)	\(^*\)to store private networks and names of computers on LAN	cat /etc/hosts	127.0.0.1&nbsp; localhost4 localhost4.localdomain4 <br>::1&nbsp; &nbsp; &nbsp; &nbsp; localhost6 localhost6.localdomain6	linux_01_code

/etc/passwd	system file	Contains user account info	e.g., home, shell..	cat /etc/passwd | grep "root"	root:x:0:0:root:/root:/bin/bash&nbsp;<br>steven:x:1000:1000:Steven :/home/steven:/bin/bash	linux_01_code

/etc/shells	system file	Lists all avalable shells		cat /etc/shells	/bin/sh <br>/bin/bash <br>/bin/tmux&nbsp;	linux_01_code



/dev/shm	dynamic system directory	The system's virtual memory file system		df	tmpfs&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8131940&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 752&nbsp;&nbsp; 8131188&nbsp;&nbsp; 1% /dev/shm&nbsp;<br>/dev/nvme0n1p3 481666048 44402684 436272804&nbsp; 10% /home <br>/dev/nvme0n1p2&nbsp;&nbsp;&nbsp; 999320&nbsp;&nbsp; 249504&nbsp;&nbsp;&nbsp; 681004&nbsp; 27% /boot	linux_01_code

/	system directory (I)	Root (directory) of the fs	Fedora uses the File System Hierarchy Standard<br><a href="https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.html">https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.html</a>	ls /	bin/ dev/&nbsp; home/&nbsp; lib64@&nbsp;&nbsp;&nbsp;&nbsp; media/&nbsp; opt/&nbsp;&nbsp;&nbsp; root/&nbsp; sbin@&nbsp; sys/&nbsp; usr/ <br>boot/&nbsp; etc/&nbsp; lib@&nbsp;&nbsp; lost+found/&nbsp; mnt/&nbsp;&nbsp;&nbsp;&nbsp; proc/&nbsp;&nbsp;&nbsp; run/&nbsp;&nbsp; srv/&nbsp;&nbsp; tmp/&nbsp; var/<br><div></div>	linux_01_code

/dev	system directory (II)	Device files	e.g., disks, cpu, memory (~<b>udevd</b>)<br><br><a href="https://docs.fedoraproject.org/en-US/Fedora/14/html/Storage_Administration_Guide/s1-filesystem-fhs.html">https://docs.fedoraproject.org/en-US/Fedora/14/html/Storage_Administration_Guide/s1-filesystem-fhs.html</a>	ls /dev	nvme0n1 sda cpu/ mem	linux_01_code

/etc	system directory (II)	Host-specific system configurations	I.e.: the major location of&nbsp;<i>system-wide</i>&nbsp;config files<br><br><a href="https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch03s07.html">https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch03s07.html</a>	ls /etc	kernel lvm cups cockpit nfs.conf	linux_01_code

/etc/cups	system directory	Global config files for CUPS	e.g., default print server	ls /etc/cups	classes.conf&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br>client.conf	linux_01_code

tail	command	Output only the <i>last</i> parts of a file/standard output\(^*\)	\(^*\)default is 10	ls /etc/modules | tail	5.14.16-301.fc35.x86_64/ <br>5.14.17-301.fc35.x86_64/ <br>5.14.18-300.fc35.x86_64/&nbsp;	linux_01_code

head	command&nbsp;	Output only the <i>first</i> parts of a file/standard output\(^*\)	\(^*\)default is 10	journalctl --list-boots | head&nbsp;	-52 e26fdjdahjhdas 2021-09-07 14:42:45 CEST&nbsp;	linux_01_code



/etc/systemd	system directory	Configuration files for Systemd		ls /etc/systemd	journald.conf coredump.conf	linux_01_code

/etc/X11	system directory	Global config files for the X window system (xorg)		ls /etc/X11	xinit/&nbsp; Xmodmap&nbsp; xorg.conf.d/&nbsp; Xresources&nbsp; Xsession.d/&nbsp;	linux_01_code

/lib	system directory (II)	Essential shared libraries and kernel modules	e.g. the C programming code library needed to boot the system and run the commands in the root filesystem	ls /lib	grub&nbsp; &nbsp;modeprobe.d&nbsp; &nbsp; systemd&nbsp; &nbsp; rpm	linux_01_code

/lib/modules	system directory	Kernel modules		ls /lib/modules | tail	5.15.8-200.fc35.x86_64/	linux_01_code

/proc	system directory (II)	Pseudo fs documenting the kernel and processes as text files	I.e.: The information base for commands displaying running processes	ls /proc&nbsp;	/&nbsp;&nbsp;&nbsp;&nbsp; 17/&nbsp;&nbsp;&nbsp; 2025/&nbsp;&nbsp; 29848/ cpuinfo	linux_01_code

/sbin	system directory (II)	Sytem binaries	\(^*\)I.e. commands to boot, restore, recover or repair the system (in addition to binaries in /bin)	ls /sbin	fsck.8.gz<br>swapon*&nbsp;	linux_01_code

/usr	system directory (II)	(Multi-)user utilities and applications	I.e.: Everything available to the Linux user<br>E.g. binaries, their documentation, libraries, header files	ls /usr	bin/&nbsp; games/&nbsp; lib/&nbsp; libexec/&nbsp; sbin/&nbsp;&nbsp; src/ <br>etc/&nbsp; include/&nbsp; lib64/&nbsp; local/&nbsp; &nbsp;share/&nbsp; tmp@&nbsp;	linux_01_code

/usr/sbin	system directory	Commands to manage the user accounts, holding files open, daemon processes, printers, service requests		ls /usr/sbin	wpa_supplicant* <br>mkfs.ext3*<br>cupsd<br>sshd	linux_01_code

/usr/share/man/man8	system folder	A list of all administrative commands	I.e.: Intented for the system administrator	ls /usr/share/man/man8 | less	clock.8.gz <br>cockpit-tls.8.gz&nbsp;	linux_01_code


/home	system directory	User Home Directories	Major location of&nbsp;<i>personal</i>&nbsp;config files	ls ~/.*	.R .ssh .local .vim&nbsp;	linux_01_code


/dev/sd<...>	dynamic system directory	USB devices		lsblk	sda&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8:0&nbsp;&nbsp;&nbsp; 1&nbsp; &nbsp; &nbsp;15G&nbsp; 0 Massstorage	linux_01_code

/etc/sudoers	system file	Manages (root) users and group priveleges using sudo		sudo cat /etc/sudoers | grep "root"	## Allow root to run any commands anywhere  <br>root&nbsp;&nbsp;&nbsp; ALL=(ALL)&nbsp;&nbsp;&nbsp;&nbsp; ALL&nbsp;	linux_01_code

/etc/profile.d	system directory	Dir from which /etc/profile gathers shell settings	execute: first log in			linux_01_code

/etc/bashrc	system file	(System-wide) commands every non-login shell executes	- executes: @1st login, opening<br>- overwritten by ~/.bashrc			linux_01_code

~/.bashrc	system file	(User) commands every non-login shell executes	Executes: @login, opening<br>Use: aliases			linux_01_code

~/.bash_logout	system file	(User) commands executed each time you log out				linux_01_code


<ol><li>{{c1::usr/local/bin}}</li><li>{{c1::usr/local/sbin}}</li></ol>	system directory	Directories to add my commands	\(^* \because\) directories are usually added to $PATH, can overwrite commands of the same name	ls /usr/local/bin		Cloze

<ol><li>{{c1::/usr/local/bin}}</li><li>{{c1::/usr/local/sbin}}</li><li>{{c2::/opt/bin}}</li></ol>	system directories	3rd party commands\(^*\)	\(^*\)not included with the Linux distro	ls /usr/local/bin		Cloze

system directories	<ol><li>{{c1::/usr/local/bin}}</li><li>{{c1::/usr/local/sbin}}</li><li>{{c2::/opt/bin}}</li></ol>	3rd party commands\(^*\)	\(^*\)not included with the Linux distro	ls /usr/local/bin		Cloze




## System Admin

{{c1::su}} {{c1::-}} {{c1::<user>}}	command and arguments	Open a new shell as &lt;user&gt;		su - steven	Password:  <br>[steven@eryn ~]$ 	Cloze


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


