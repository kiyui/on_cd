on_cd
=====
Run scripts and programs when entering a specific directory.

# Setting up
* Install on_cd anywhere in $PATH or run the `install` script
* Add this to your shell rc (eg. bashrc)
```
function cd()
{
    builtin cd "$*" && on_cd
}
```
* Optionally, create ~/.on_cdrc to change values
```
# Script file
cds="./.on_cd"
# Script lock file
cdl="./.on_cd_lock"
# Script detect message
cdm="$txtred""Press ENTER to run script.\n""$txtrst"
# Script quit message
cdq="$txtred""Quit""$txtrst"
```

# Usage
Create a script called `.on_cd` in a directory. View `.on_cd` for an example.

# Example Script
```
#!/bin/sh
function script() {
    git status
    git fetch
}

script

# Background tasks
executables=("php artisan serve" "gulp watch")
```
