# toblib-go
thinobject library to explore Go packages and files

##  Go

Thinobject library Go directory is just a placeholder with no methods (so far).

##  Go/Package/
        ^ -> Directory

Thinobject library type Go/Package is a Directory object, representing a directory
containing one or more *.go files under a certain package.

Methods:

### Go/Package.shadow-gofile

Given a NAME.go file, create dot-directory .NAME.go shadowing the file, and set to
the Go/Package/GoFile thinobject type.  A symlink is set to the source *.go file.

### Go/Package.build

This method may be misplaced...


##  Go/Package/GoFile
    ^ -> Directory

Thinobject library type Go/Package/GoFile is a Directory object representing a directory
representing a single *.go file.

Methods:

### Go/Package/GoFile.parse-gofile

The Go/Package/GoFile.parse-gofile method parses the source *.go file into separate
elements as list files, including the package name and global variables, constants, types,
functions, and methods.  List file @ORDER contains an entry (in order) for each element.


### Go/Package/GoFile.build-gofile

The Go/Package/GoFile.build-gofile method reads the @ORDER list file and concatenates 
each element list file to construct a *.go output file.


### Go/Package/GoFile.list-to-symvars

The Go/Package/GoFile.list-to-symvars method reads one or more given element list files,
or processes each element file in @ORDER, and tries to create a symvar representing each
variable or constant declaration.

This method should also be extended to create symvars for other declarations, including
types and perhaps more.


### Go/Package/GoFile.clean-object

The Go/Package/GoFile.clean-object method reads @ORDER and deletes each list file listed.


### examples

This ordinary directory contains various examples to flesh out the workings of the list-to-symvars
method.  Each subdirectory should be a Go/Package/GoFile type.


