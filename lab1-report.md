# Lab 1 Report
> Jefferson Umanzor
---

## Command Tests
### `cd` Tests

`cd` With No Arguments
```
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ pwd
/home
```
- `cd` with no arguments returns you to the home directory.
- In this example, the working directory was `/home/lecture1`. I used `cd` to return to the `/home` directory from the `/home/lecture1` directory.

`cd` With A Directory Path
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ pwd
/home/lecture1
```
- `cd` with a directory path takes you to the directory as long as the directory exists.
- In this example, the working directory was `/home`. I used `cd` to change to the `/home/lecture1` directory from the `/home` directory.

`cd` With A File Path
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/Hello.java
bash: cd: lecture1/Hello.java: Not a directory
```
- `cd` with a file path does not take you to the file. It returns an error message stating the argument is not a directory because `cd` is meant to travel between directories.
- In this example, the working directory was `/home`. I attempted to travel to the file `/lecture1/Hello.java` using `cd`. Thus, an error returned because `/lecture1/Hello.java` is a file, not a directory.


### `ls` Tests

`ls` With No Arguments
```
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
- `ls` with no arguments returns a list of the contents of the current directory or returns an error message if you are currently inside a file because `ls` is meant to print the content of directories.
- In this example, the working directory was `/home/lecture1`. I used `ls` while inside the `/home/lecture1` directory to return a list of the contents of the directory.
  
`ls` With A Directory Path
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1/messages
en-us.txt  es-mx.txt  fr.txt  zh-cn.txt
```
- `ls` with a directory path returns a list with the directory's content as long as the directory exists.
- In this example, the working directory was `/home`. I used `ls` from the `/home` directory and passed a path for the `/lecture1/messages` directory to return a list of the contents of the `/lecture1/messages` directory.

`ls` With A File Path
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1/Hello.java
lecture1/Hello.java
```
- `ls` with a file path returns the path of the file as long as the file exists.
- In this example, the working directory was `/home`. I used `ls` with the `/lecture/Hello.java` file path which returned the `/lecture1/Hello.java` file path.

### `cat` Tests

`cat` With No Arguments
```
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$ cat
duplicate my text
duplicate my text
```
- `cat` with no arguments allows you to input text that is outputted in return. Click Ctrl+C to exit.
- In this example, the working directory was `/lecture1`. I used `cat` with no argument which duplicated the input "duplicate my text."

`cat` With A Directory Path
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1/messages
cat: lecture1/messages: Is a directory
```
- `cat` does not print out the directory. It returns an error message stating that the argument is a directory because `cat` is meant to be used to print the content of files. It will also return an error if the directory does not exist.
- In this example, the working directory was `/home`. I used `cat` with a path to the `/lecture1/messages` directory which returned an error because `/lecture1/messages` is not a file.

`cat` With A File Path
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1/Hello.java
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
- `cat` with a file path prints out the file's content as long as the file exists.
- In this example, the working directory was `/home`. I used `cat` with a path to the `/lecture1/Hello.java` file which printed the content of the `/lecture1/Hello.java` file.
