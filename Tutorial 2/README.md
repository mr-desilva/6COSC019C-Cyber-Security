## Tutorial 2
- [Tutorial 2](#tutorial-2)
  - [Linux File System](#linux-file-system)
  - [Linux file system navigating commands.](#linux-file-system-navigating-commands)
  - [Linux file system, file manipulating files and directories.](#linux-file-system-file-manipulating-files-and-directories)
- [|cat|To display a text file within the terminal|](#catto-display-a-text-file-within-the-terminal)
  - [Linux file permission](#linux-file-permission)
  - [Networking](#networking)
  - [Adding or removing software](#adding-or-removing-software)
  - [Pipes and connecting things](#pipes-and-connecting-things)

----------

* To enter the super user mode in vm enter
`sudo su` and then enter the password.

* To open a file from terminal using Vim use `sudo vim filename`. 

* Edit mode `Insert` key. Then press esc and enter `:w` will save the file. Then `:q` to exit.

----------

### Linux File System

|/bin|User binaries|
|:----|:----|
|/sbin|System binaries|
|/etc|Configuration files|
|/dev|Device files|
|/proc|Process information|
|/var|Variable files|
|/tmp|Temporary files|
|/usr |User programs|
|/home|Home directories|
|/boot|Boot loader files|
|/lib|System libraries|
|/opt|Optional applications|
|/mnt|Mount directory|
|/media |Removable devices|
|/srv|Service data|

----------


### Linux file system navigating commands.
|pwd|Identify current working directory|
|:----|:----|
|ls|List the files and directories within the current working directory|
|cd|To change the current working directory|
|File|Determine type of a file|
|less|View text files|

----------

### Linux file system, file manipulating files and directories.
|mkdir|Create new directories|
|:----|:----|
|cp|Copies files and directories|
|mv|File moving and renaming|
|rm|Remove files|
|cat|To display a text file within the terminal|
----------
### Linux file permission
|Permission|Symbol|Description|
|:----|:----|:----|
|Read|R|The user can read the content of the file or directory|
|Write|W|The user can modify the file or directory|
|Execute|X|The user can execute the file or access the directory|

`It is not recommended to use the su command. Su command give you full root privilege for everything you do afterwards and do not ask you for a password. This can be dangerous and can break the file system by mistakenly.`

### Networking
1. Getting IP
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img1.png" width="712" height="465">
2. Bringing down a specific network interface
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img2.png">

    To bring up use >> sudo ifconfig eth0 up
3. Assigning a custom ip address for the network interface using command line.
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img3.png" width="712" height="465">

----------

### Adding or removing software

Use sudo apt-get upgrade to regularly update the software repository list.
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img4.png" width="712" height="465">

----------

### Pipes and connecting things
1. Pipe take the output of one command and send it to another.
Cat command will not display longer text. Using head command can view the number of lines needed to display.

<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img5.png">

2. Here displaying the top 3 lines in the document.
Using the tail command can view the lines from the bottom.
 
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img6.png">

3. We can use the grep command to search files for matching patterns.
Bellow example shows finding the matching word ‘document’ within the text file.

<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img7.png">

4. Using -n can find the number of matching results.

<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%202/images/img8.png">

Awk command is used to extract specific text from a file according to a rule.
