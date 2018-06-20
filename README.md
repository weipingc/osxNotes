[Good bash_profile: https://natelandau.com/my-mac-osx-bash_profile/](https://natelandau.com/my-mac-osx-bash_profile/)
    export PS1="________________________________________________________________________________\n| \w @ \h (\u) \n| => "
    export PS2="| => "
  
Find files then grep text:
    find . -name '*.py' -exec grep 'something' {} \; > output.txt // grep executed as many times as FIND finds occurences.
    find . -name '*.py' -exec grep 'something' {} \+ > output.txt // the output from find concatenated

List directories and their sizes in Mac OS X command line:
    du -hs dir

Display hidden files in Finder
    [OSX finder show hidden files](https://ianlunn.co.uk/articles/quickly-showhide-hidden-files-mac-os-x-mavericks/):
        defaults write com.apple.finder AppleShowAllFiles YES
    
