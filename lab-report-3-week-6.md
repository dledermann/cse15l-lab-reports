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

public key stored in Github

![image](Screen Shot 2022-05-06 at 5.30.15 PM.png)

private key stored on my computer

![image](Screen Shot 2022-05-06 at 5.52.33 PM.png)

git commit and push used on ieng6 server

[Link to commit](https://github.com/dledermann/markdown-parser/commit/961eb5ceb91b594779e3f4f4502e789eb5853e68)

## Copy whole directories with scp -r

![image](Screen Shot 2022-05-06 at 6.36.06 PM.png)

markdown-parse file being copied over to ieng6 account

![image](Screen Shot 2022-05-06 at 6.38.18 PM.png)

markdown-parse file tests being compiled and ran on the ieng6 account

![image](Screen Shot 2022-05-06 at 6.59.09 PM.png)

combination of scp , ;, and ssh beign used to scp the directory to ieng6 account, then compiling and running the tests.