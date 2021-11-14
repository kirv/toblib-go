# toblib-go
thinobject library to explore Go packages and files

## What is **thinobject**?

*thinobject* is a set of conventions regarding file and symlink names and an executive function 'tob'
to run queries of the form: 'object.method' at a bash command line prompt.

*thinobject* uses an executive function, ```tob``` to execute commands at a bash terminal prompt.  The
commands are passed to ```tob``` by the bash(1) *command_not_found_handle()* function.  Thinobject commands
are of the form OBJECT.METHOD, where OBJECT is a file or directory visible to the caller, and METHOD is an
executable script or program resolved by ```tob``` for OBJECT.

Thinobject methods run in the context directory of the object, since ```tob``` changes to the object 
directory before exec'ing the method.

A *thinobject* object is a directory containing a symlink named ^ (caret) with a non-resolving symlink
value that is the *type* of the object.


##  Go

Thinobject type *Go* directory is just a placeholder with no methods (so far).

##  Go/Package/

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


