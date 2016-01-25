on_cd
=====
Run scripts and programs when entering a specific directory. on_cd supports:
* Foreground tasks
* Background tasks
* Gracefully exiting applications

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
You can have optional background tasks in an array called `executables` as in the "Example Script" section.

# Example Script
This example checks the repository status and fetches any updates from origin. It also provides background tasks for `on_cd` ro run. In this example, the `.on_cd` script is placed in a Laravel 5 development directory where a test server and gulp are executed.

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
