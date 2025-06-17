##BANDIT


###bandit0:
	using SSH connect to the host using  provided host link @ the specified port
	(password and username is already provided)
	<br>commands -> `ssh [-p]` 

###bandit1:
	list the content of the file. Use `./` for explicitly specifying the filename
	<br>commands -> cat 

###bandit2:
	use \ when you need to type filenames with spaces. 
	<br>example "hello world" can be typed as hello\ world

###bandit3: 
	hidden filenames begin with "." example ".hellowold"

###bandit4: 
	find the filetype of all files. All the files in a location can be
	specified using a special symbol "*". example cat ./*
	<br>commands -> `file` 

###bandit5:
	search for the file using `find` by specifying the provided matching info
	<br>commands -> `find [-type] [-size]`
	<br>extra -> addding `2>&1 | grep -v "Permission"` filter out
	
	 
	 

