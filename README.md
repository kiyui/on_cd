on_cd
=====
Run scripts when you cd into a directory,
because that's what the cool kids are doing.

Setting up
==========
* Install on_cd anywhere in $PATH
* Add this to your shell rc (eg. bashrc)
```
function cd()
{
    builtin cd "$*" && on_cd
}
```
* Optionally, create .on_cdrc to change values
```
cdm="on_cd detected x:\\\n:q"
cdq="Quit"
```

Warning 
=======
Someone can easily set up on_cd scripts
on your computer so be sure you know what you're
doing. Keep tuned for updates including better
security.

FAQ
===
* Dude wth??!
- Yes.
