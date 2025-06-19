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


	
	 
	 

