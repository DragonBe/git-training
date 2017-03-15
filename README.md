# Git training - The basics


// Creating a new branch

Ga naar de repository
Fork de originele repository
Ga naar de fork in je eigen github profiel
Kopieer de link van de Fork
Git clone <link van fork>
Git checkout -b <BranchName>
Git add -A
Git commit -m "Voeg hier je commentaar toe"

How to change your bash profile:

First dive into your directory and add following lines to `vi ~/.bash_profile`:
```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```

Next change your source with the following command `source ~/.bash_profile`

Now you'll notice some beautiful colors are added in your terminal!
