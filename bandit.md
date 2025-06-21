## BANDIT


### bandit0 :
using SSH connect to the host using  provided host link @ the specified port.
(password and username is already provided)
<br> NB: `ssh [-p]` 

### bandit1 :
list the content of the file. Use `./` for explicitly specifying the filename.
<br>NB: `cat` 

### bandit2 :
use `\` when you need to type filenames with spaces. 
<br>example "hello world" can be typed as `hello\ world`

### bandit3 : 
hidden filenames begin with `.` example `.hellowold`.

### bandit4 : 
find the filetype of all files. All the files in a location can be
specified using a special symbol `*`. 
<br>example `cat ./*`
<br>NB: `file` 

### bandit5 :
search for the file using `find` by specifying the provided matching info.
<br>NB: `find [-type] [-size]`
<br>extras: adding `2>&1 | grep -v "Permission"` filter out lines containing the string "Permission"

### bandit6 :
search for the file using `find` by specifying the provided matching info.
<br>NB: `find [-type] [-size] [-user] [-group]`
<br>extras: adding `2>&1 | grep -v "Permission"` filter out lines containing the string "Permission"

### bandit7 :
search for the line containing the PATTERN "millionth" using grep in the specified file.
<br>NB: `find` 

### bandit8 :
find uinque line in the given file using `uniq`. but for `uniq` to find unique line, the data has to be sorted first,therefore sort the file using `sort` and pipe it to `uniq` using the pipe `|` operator.
<br>NB: `uniq -[u]` `sort` `|`
<br>example: piping `ls --help` to `less` is done by `ls --help | pipe` 

### bandit9 :
find the human readable strings from the file using `strings` also use `grep` to filter out the lines that contain the given characters.(use approx 4 of the given character for grep)
<br>NB: `strings` `grep`  

### bandit10 :
decode the given base64 encoded file using `base64` 
<br>NB: `base64 [-d]` 

### bandit11 :
rotate alphabet characters of the file to 13th alphabet character coming after it in the alphabet order(this is called ROT13).ie convert a->n, b->0 etc. use `tr` for rotation. NOTE rot13 doesnt usually include nubmers and `tr` also doesnt effect the numbers in the string. `tr` takes string as input.
<br>NB: `tr` `cat`
<br>example: `echo "aAbB" | tr somestring 'a-zA-Z' 'b-zaB-ZA'` rotates each character by 1 position and gives output as "bBcC"

### bandit12 :
copy the file to a /tmp location so you have neccessary permissions.Decompress the hexdump file to binary using `xxd` and output it to a file. Find type of the output file using `file`.
* if file type is tar archive -> rename with ".tar" extension -> extract using `tar`
* if file type is gzip compressed -> rename with ".gz" extension -> decompress using `gzip`
* if file type is bzip2 compressed -> rename with ".bz" extension -> decompress using `bzip2`
<br>NB: `xxd [-r]` `file` `gzip [-d]` `bzip2 [-d]`  

### bandit13 :
ssh into bandit14 using the given bandit14 private key given. 
<br>NB: `ssh [-i] [-p]`

### bandit14 :
connect to given port using netcat. simply enter the current passwd.
<br>NB: `nc`

### bandit15 :
connect to given port using ncat it supports ssl. simply enter the current passwd.
<br>NB: `ncat [--ssl]`

	 
	 

