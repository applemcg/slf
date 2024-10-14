

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
		# mv slf_lib to $HOME/bin 
		
+ if not on your path, copy the included `path_fragment.txt` to your $HOME/.profile
		
## Next Steps, Get Acquainted

Before sourcing the shell library,  inspect the abstracts.txt file

## Final, Contact the Author










