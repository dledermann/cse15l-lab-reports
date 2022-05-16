[Home](https://dledermann.github.io/cse15l-lab-reports/)

## Streamlining ssh Configuration
![image](Screen Shot 2022-05-06 at 4.58.59 PM.png)

The .ssh/config file was edited using the nano command in the terminal.
```
$ nano ~/.ssh/config
```

![image](Screen Shot 2022-04-29 at 5.21.05 PM.png) 

Shows the server being logged into using the ieng6 alias that was set previously.

![image](Screen Shot 2022-05-06 at 5.15.22 PM.png)

Shows the scp copying a file to the server using the alias ieng6.

## Setup Github Access from ieng6

![image](Screen Shot 2022-05-06 at 5.28.27 PM.png)

public key stored in Github. Public key was added to Github by clicking the
 New SSH key button, then copying the contents of the file labeled id_rsa.pub
 in the image below. The id_rsa.pub was made in lab-report-1-week-2,
 and the contents were copied by using the command

 ```
$ cat ~/.ssh/id_rsa.pub
 ```

 and then copying the output of the command and pasting it into github.

![image](Screen Shot 2022-05-06 at 5.30.15 PM.png)

private key stored on my computer. Private key was made with the public
key in lab-report-1-week-2 using the command

```
ssh-keygen
```

Using ssh-keygen on the server, I made a public key on the server,
then I copied it into github like I did for my user account.

![image](Screen Shot 2022-05-06 at 5.52.33 PM.png)

git commit and push used on ieng6 server, because I have the public
key saved in github, so the ieng6 server can communicate with github.

[Link to commit](https://github.com/dledermann/markdown-parser/commit/961eb5ceb91b594779e3f4f4502e789eb5853e68)

## Copy whole directories with scp -r

![image](Screen Shot 2022-05-06 at 6.36.06 PM.png)

markdown-parse file being copied over to ieng6 account.
-r makes scp repeat recursively and the . is the current directory,
so scp -r . makes scp repeat recursively for the current directory. 
ieng6 is the server and the ~/markdown-parse creates a directory on
the ieng6 server that has the name markdown-parse, then stores the
files that were transferred using scp in this directory.

![image](Screen Shot 2022-05-06 at 6.38.18 PM.png)

markdown-parse file tests being compiled and ran on the ieng6 account.
The ieng6 server was logged onto, then the directory was changed to the
newly created markdown-parse directory, which stored copied files. 
Once in the directory, the javac statement is the statement that was used
to compile the MarkdownParseTest java file with the class path for junit
and hamcrest, then the java statement runs the .class file that was created
from the javac statement. The output is the junit output, which successfully
passed all the tests.

![image](Screen Shot 2022-05-06 at 6.59.09 PM.png)

combination of scp , ;, and ssh beign used to scp the directory to ieng6 account, then compiling and running the tests.
the *.java and *.md make is so that only files that end with .md or .java in the current directory are copied recursively,
and the lib/ makes it so that the folder with that name is copied with all its contents. The scp -r and ieng6:~/markdown-parse
do the same thing and after the ieng6:~/markdown-parse, a semicolon is there to separate commands. Once on ieng6 server,
the portion after the semicolon is ran. The portion after the semicolon runs the javac on the MarkdownParseTest.java file
using the version of java on the ieng6 server, because my mac isn't compatible with the current java version. The same thing
is done to run the MarkdownParseTest.class file, where the location of java is included, so that it uses the servers version
of java and not mine. As shown in the image, the .md, .java, and lib/ folder and files are copied and then the junit tests run
and they are all passed.