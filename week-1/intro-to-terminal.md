_With credit to [Calvin Webster](http://github.com/calweb) for much of the content._

## Terminal

The terminal is a developer's best friend, and will be used throughout the course. Once experienced at using a terminal, you'll find that doing many things in programming are simpler and more efficient. You'll effectively be able to accomplish more and have a better understanding of what's going on in your application.

Following are some of the commands we covered today:

### Navigation in Terminal

```
$ ls
Applications
Desktop
Documents
Downloads
```
 Lists the contents of the current directory you are in.

```
$ ls -al

drwx------     4 calvinwebster  staff     136 Dec 11 01:11 Applications
drwx------+   20 calvinwebster  staff     680 Jan  5 10:13 Desktop
drwx------+   56 calvinwebster  staff    1904 Jan  5 10:09 Documents
drwx------+  193 calvinwebster  staff    6562 Dec 29 15:27 Downloads

```
When <code>$ ls</code> is used with the <code> -al</code> flags, it will give you more information about the file and/or directories such as when it was last modified, the file/folder permissions, and the user that owns the file/folder.

```
$ pwd
/Users/yourusername

```
prints out the path of the current working directory in your file system.

```
$ cd Documents

```
The above command will navigate you inside of the Documents folder

### Creating files folders in terminal

```
$ mkdir myDirectoryName

```
Creates a directory

```
$ touch myFile.txt

```
Creates a new file.

```
$ cat myFile.txt

```
Reads the contents of myFile.txt in your shell.

```
$ echo "I am going into myFile" >> myFile.txt

```
Adds the line "I am going into myFile" to myFile.txt
