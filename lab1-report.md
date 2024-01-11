# Lab 1 Report
> Jefferson Umanzor

---

## Command Tests
**`cd` Tests**

`cd` With No Arguments
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ pwd
/home
```
- `cd` with no arguments returns you to the home directory.

`cd` With A Directory
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
- `cd` with a directory takes you to the directory as long as the directory exists.

`cd` With A File
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
- `cd` with a file does not take you to the file. It returns an error message stating the argument is not a directory because `cd` is meant to travel between directories.

**`ls` Tests**

`ls` With No Arguments
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
- `ls` with no arguments returns a list of the contents of the current directory.

`ls` With A Directory
```
[user@sahara ~/lecture1]$ ls messages
en-us.txt  es-mx.txt  fr.txt  zh-cn.txt
```
- `ls` with a directory returns a list with the content of the directory passed as the argument as long as the directory exists.

`ls` With A File
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```
- `ls` with a file returns the name of the file as long as the file exists.

**`cat` Tests**

`cat` With No Arguments
```
[user@sahara ~/lecture1]$ cat
duplicate my text
duplicate my text
```
- `cat` with no arguments allows you to input text that is outputted in return.

`cat` With A Directory
```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
```
- `cat` does not print out the directory. It returns an error message stating that the argument is a directory because `cat` is meant to be used to print the content of files. It will also return an error if the directory does not exist.

`cat` With A File
```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
```
- `cat` with a file prints out the content of the file as long as the file exists.
