## BANDIT


### bandit0 -> 1 :
1. list the contents of readme file provided using `cat` 
2. using SSH connect to the host using  provided host link @ the specified port.
(password and username is already provided)
<br> NB: `ssh [-p]` 

### bandit1 -> 2 :
list the content of the file. Use `./` for explicitly specifying the filename.
<br>NB: `cat` 

### bandit2 -> 3 :
use `\` when you need to type filenames with spaces. 
<br>example "hello world" can be typed as `hello\ world`

### bandit3 -> 4 : 
hidden filenames begin with `.` example `.hellowold`.

### bandit4 -> 5 : 
find the filetype of all files. All the files in a location can be
specified using a special symbol `*`. 
<br>example `cat ./*`
<br>NB: `file` 

### bandit5 -> 6 :
search for the file using `find` by specifying the provided matching info.
<br>NB: `find [-type] [-size]`
<br>extras: adding `2>&1 | grep -v "Permission"` filter out lines containing the string "Permission"

### bandit6 -> 7 :
search for the file using `find` by specifying the provided matching info.
<br>NB: `find [-type] [-size] [-user] [-group]`
<br>extras: adding `2>&1 | grep -v "Permission"` filter out lines containing the string "Permission"

### bandit7 -> 8 :
search for the line containing the PATTERN "millionth" using grep in the specified file.
<br>NB: `find` 

### bandit8 -> 9 :
find uinque line in the given file using `uniq`. but for `uniq` to find unique line, the data has to be sorted first,therefore sort the file using `sort` and pipe it to `uniq` using the pipe `|` operator.
<br>NB: `uniq -[u]` `sort` `|`
<br>example: piping `ls --help` to `less` is done by `ls --help | pipe` 

### bandit9 -> 10 :
find the human readable strings from the file using `strings` also use `grep` to filter out the lines that contain the given characters.(use approx 4 of the given character for grep)
<br>NB: `strings` `grep`  

### bandit10 -> 11:
decode the given base64 encoded file using `base64` 
<br>NB: `base64 [-d]` 

### bandit11 -> 12 :
rotate alphabet characters of the file to 13th alphabet character coming after it in the alphabet order(this is called ROT13).ie convert a->n, b->0 etc. use `tr` for rotation. NOTE rot13 doesnt usually include nubmers and `tr` also doesnt effect the numbers in the string. `tr` takes string as input.
<br>NB: `tr` `cat`
<br>example: `echo "aAbB" | tr somestring 'a-zA-Z' 'b-zaB-ZA'` rotates each character by 1 position and gives output as "bBcC"

### bandit12 -> 13 :
copy the file to a /tmp location so you have neccessary permissions. decompress the hexdump file to binary using `xxd` and output it to a file. Find type of the output file using `file`.
* if file type is tar archive -> rename with ".tar" extension -> extract using `tar`
* if file type is gzip compressed -> rename with ".gz" extension -> decompress using `gzip`
* if file type is bzip2 compressed -> rename with ".bz" extension -> decompress using `bzip2`
<br>NB: `xxd [-r]` `file` `gzip [-d]` `bzip2 [-d]`  

### bandit13 -> 14 :
ssh into bandit14 using the given bandit14 private key given. 
<br>NB: `ssh [-i] [-p]`

### bandit14 -> 15 :
connect to given port using netcat. simply enter the current passwd.
<br>NB: `nc`

### bandit15 -> 16 :
connect to given port using ncat, it supports ssl. simply enter the current passwd.
<br>NB: `ncat [--ssl]`

### bandit16 -> 17 :
find the open ports using `nmap` default scan (full tcp scan if no sudo) on the given ports range. then check for ssl support by connecting to each open port using `openssl s_client`. only one server is correct but entering the passwd may sometime fail because the first character of the passwd may trigger `s_client` connected commands. ways to prevent this can be found under "connected commands" section of `man openssl s_client`. the output would be a private key for ssh into next level.
<br>NB: `nmap [-sT] [-p]` `openssl s_client [-connect] [-ign_eof]` 

### bandit17 -> 18 :
store the private key from previous level to a file and modify it using `chmod`  to have only 400 permission. this permission number is required for it to be accepted as a ssh key. `ssh` using the file. use `diff` to find the change between the provided two files.
<br>NB: `chmod 400` `ssh [-p]` `diff` 

### bandit18 -> 19 :
ssh can also be used to execute commands even if nologin is specifed. use `cat` to read the contents of file "readme"
<br>example `ssh username@hostname ls`
<br>NB: `ssh [-p]` `cat`

### bandit19 -> 20 :
`setuid` on an executable allows the file to be executed as the owner of the file even if other user is running the file. the file given here would have `setuid` enabled and can be confirmed by the presence `s` in the permission of the file when using `ls -l`. the executable file given in bandit19 specifically executes any command given as its argument. hence use the executable file to `cat` the content of `/etc/bandit_pass/bandit20` where the passwd for bandit20 is stored.
<br>NB: `ls -l` `cat`	 
	 
### bandit20 -> 21 :
a port have to be created for the provided executable to listen to and we have to pass bandit20 passwd to it. the executable file would then send back the passwd for bandit21
1. start listening on a port using `nc` . 
2. pause it using Ctrl + Z and resume it in background using `bg`
3. connect the executable to the port running `nc` ,also add "&" at the end of the command so that it runs directly in background
4. bring back `nc` process to foreground using `fg`
5. enter the bandit20 passwd 

<br>NB: `nc [-l]` `fg` `bg` `jobs` 

### bandit21 -> 22 :
list the chronjob files in `etc/chron.d/`.list the details of bandit22_chronjob .`cat` the contents of the executable file inside the chronjob file. `cat` the contents of dump file listed in the executable file.
<br>NB: `ls` `cat`

### bandit22 -> 23 :
list the chronjob files in `etc/chron.d/`.list the details of bandit23_chronjob .`cat` the contents of the executable file inside the chronjob file. in the script a string is converted to md5 hashsum, which is then used as the file name for dumping the passwd of bandit23. recreate the hashsum by using "bandit23" instead of $myname.
<br>NB: `ls` `cat` `md5sum`

### bandit23 -> 24 :
list the chronjob files in `etc/chron.d/`.list the details of bandit24_chronjob .`cat` the contents of the executable file inside the chronjob file. the script is owned by bandit24 and this shell program takes script file from a specific location and executes it. find the location. also create a shell script that takes passwd from`/etc/bandit_pass/bandit24` and print it to a file in `/tmp`. remember the file create in `/tmp` would be owned by bandit24 and the neccessary permissions should be given for bandit23(current id) to read the contents(bandit24 passwd) of the file. also remember that the script in the specified location was made by bandit23(current id) and enough permissions have to be given so that bandit24 can execute it. wait for 1 min after this. you may have to wait about 1 min for the shell script to be executed
<br>NB: `chmod` `vim` `cat` `ls`

### bandit24 -> 25 :
create a simple for loop from 1000 to 9999 with the format `echo "passwd number"` and pipe it to `nc host portnumber`  
<br>example for loop printing "hello 1" to "hello 5" : `for i in {1..5}; do echo "hello $i"; done`
<br>NB: `nc`

### bandit25 -> 26 :
Now this is a special one ...for this you have to think out of the box,literally if using a tiling window manager. 
1. find the login shell assigned for bandit26 from the file `/etc/passwd`
2. analyse the content of the shell specified
<br>note a command line tool `more` is getting executed as the only main process, as `more` completes execution, the shell is closed and the connection is lost. `more` is a tool that is used to display data in way that fits the terminal size.`more` also support other actions like opening `vim`. hence we have to somehow stop `more`from completing its execution for anythin else.
so to prevent `more` from completing its execution, we have to stop it from displaying the entire data. 
5. for this we have to reduce the terminal height so that there is not enough height for the data to be displayed completely.(tbh i had to google for the resizing hint,and i was blown away seeing the hint... literally made me laugh aloud!😆)
6. login using the provided ssh private key
7. open edit mode from `more`
8. set appropriate `shell` for vim to use
9. open shell from vim
10. passwd is obtainable from `etc/bandit_pass/bandit26`
<br>NB: `more` `vim` `cat` 

### bandit26 -> 27 :
use the `setuid` enabled file in bandit26 home directory to obtain the passwd for bandit27
<br>NB: `cat`

### bandit27 -> 28 :
clone the git using the `ssh` format with custom port, and `cat` the contents
<br> example `git clone ssh://user@hostname:portnumber/path/to/repo.git`
<br> `git clone` `cat`

### bandit28 -> 29 :
clone the git and go to a previous commit 
<br>NB: `git [log] [checkout]` 

### bandit29 -> 30 :
clone the git and change the brach
<br>NB: `git [log] [checkout] [branch]` 

### bandit30 -> 31 :
clone the git and list the tags and use a tag
<br>NB: `git [tag] [show *tagname*]






