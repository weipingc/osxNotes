[Good bash_profile: https://natelandau.com/my-mac-osx-bash_profile/](https://natelandau.com/my-mac-osx-bash_profile/)
    export PS1="________________________________________________________________________________\n| \w @ \h (\u) \n| => "
    export PS2="| => "
  
Find files then grep text:
>    find . -name '*.py' -exec grep 'something' {} \\; > output.txt

(grep executed as many times as FIND finds occurences.)

>    find . -name '*.py' -exec grep 'something' {} \\+ > output.txt

(grep executes once against the output from find concatenated)

This command (with -print) outputs more lines b/c -print prints every found file's name, and you can know which file contains the content)

> find . -name "*.gradle" -print -exec grep 'gw-gunit-build' {} \\;

than

> find . -name "*.gradle" -exec grep 'gw-gunit-build' {} \\;


# Define a function so we can find strings within files like:
#     findgrep <file-name-pattern> <string-pattern>
#       (grep executes once against the output from find concatenated)
#     findgrepm <file-name-pattern> <string-pattern>
#       (grep executed as many times as FIND finds occurences, use it when output of find command is TOO big)
# Example:
#    findgrep '*.xml' 'jetty'
function findgrep()  { find . -name "$1" -exec grep "$2" {} \+ > /tmp/findgrep.txt 2> /dev/null ; wc -l /tmp/findgrep.txt ; }
function findgrepm() { find . -name "$1" -exec grep "$2" {} \; > /tmp/findgrep.txt 2> /dev/null ; wc -l /tmp/findgrep.txt ; }
function findrm()  { find . -name "$1" -exec rm -R {} \+ > /tmp/findrm.txt 2> /dev/null ; }
function findrmm() { find . -name "$1" -exec rm -R {} \; > /tmp/findrm.txt 2> /dev/null ; }
function findgunzip() { find . -name "*.gz" -exec gunzip {} \+ > /tmp/findgunzip.txt 2> /dev/null ; }


List directories and their sizes in Mac OS X command line:
    du -hs dir

Display hidden files in Finder
    [OSX finder show hidden files](https://ianlunn.co.uk/articles/quickly-showhide-hidden-files-mac-os-x-mavericks/):
        defaults write com.apple.finder AppleShowAllFiles YES
    
