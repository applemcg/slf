

# Shell Library 101

This is the introductory course to Shell Libraries.  It is made up of
a handful of specific functions with a few thrown in as place-holders
for follow-up lessons.

## Having saved the email attachments

+ move these three files to a separate place, for example:

        $ set $HOME/lib/slf101
        $ mkdir -p  $1

## First Steps, Installation

If you haven't yet,

+ unpack the shell archive

        $ cd       $1
        $ chmod +x  slf101.sh
        $ ./slf101.sh    # unpacks the shell archive, source later
        $ chmod +x slf_lib

+ move the library to your path

        $ mkdir $HOME/bin           # if you don't have one
		# cp slf_lib to $HOME/bin 
		
+ if not on your path, copy the included `path_fragment.txt` to your $HOME/.profile
		
## Next Steps, Get Acquainted

Before sourcing the shell library, inspect the abstracts.txt file.

It's possible to view function two ways:

1. view the library in a view-only editor #  $ view $(which slf_lib) 
1. source the library in a sub-shell and display the function body

Since the latter means may be new to you, here's how:

>   $ ( source $(which slf_lib); declare -f slf_help )  # the parens define the sub-shell

Now, do this one:

>   $ ( source $(which slf_lib); declare -f fbdy );     # you see the function, d
>   $ declare -f fbdy                                   # but not here.

By inspecting the library completely, satisfy yourself you are comfortable in
allowing it's contents into your shell environment.  Simply conduct these steps:

	$ source $(which slf_lib)  # and begin to examine its features
    $ fbdy                     # with no arguments
	$ sfg1 ...                 # Set Functions Group ...,  e.g.
	$ sfg1 slf_                # names and uses of slf_
	$ slf_list fbdy            # you will likely need to Pipe it
	$ slf_list fbdy | more     # and as a reminder;
	$ slf_help                 # importantlty, for future maintenance
	$ fbdy slf_init            # shows slf_init function, whihch
		                       # overwrites a local ./ copy of slf_lib

## Direction

The latter step suggests to add a function to the library, the local copy anyway,
you need to add the function to the `slf_list`, shown here:

        slf_list () 
        { 
            : Shell Library 101, library function list;
            ${*:-echo} sfg1 functions fbdy comment debug pause \
                       slf_{help,init,list}
        }

## Concepts

Four concepts appear here which may be new to you, and will be expanded upon in future
editions of Shell Library lessons.

1. the **null command**, in this case the line:

       : Shell Library 101, library function list;
       : where the leading colon starts the null command

    here is [the Null Command](https://www.gnu.org/software/bash/manual/html_node/Bourne-Shell-Builtins.html)
    
1. [the ${*:-echo} idiom](https://www.gnu.org/software/bash/manual/bash.html#Shell-Parameter-Expansion)
1. [curly brace { ,,, } shorthand](https://www.gnu.org/software/bash/manual/bash.html#Brace-Expansion)
1. Using an underscore, e.g. `slf_init` in function names introduces
   the concept of a function `family`, in this case **slf** is the
   family and *init* is the subfunction. Many subfunction names such
   as `init, help, list` as used here to handle family administrative
   functions.

These are used throughout my function repertoire, where the null
command adds these features to the collection of functions:

+ tags -- such as date, related, lesson, usage, example, ..
+ datestamp -- the date tag
+ abstract -- the first null-command line, see abstracts.txt
+ shdoc -- the null-command lines before the first tag.

There are necessary precautions in using the null-command which will be covered in a later lesson

## Final, Contact the Author

        name:  Marty McGowan
		email: martymcgowan AT alum DOT mit DOT edu
		about: http://mcgowans.org/marty3
        page:  http://mcgowans.org/marty3/slf
        text:  [README](./README.txt)
		
