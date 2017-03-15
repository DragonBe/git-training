# Git training - The basics

## Creating a new branch

Ga naar de repository
Fork de originele repository
Ga naar de fork in je eigen github profiel
Kopieer de link van de Fork

```
git clone <link van fork>
git checkout -b <BranchName>
git add <filename>
git commit -m "Voeg hier je commentaar toe"
```

Indien je een merge conflict hebt :
(zorg dat de usptream correct is) 
```
git remote add upstream <link naar originele repo>
git checkout master
git pull upstream master
git checkout <BranchName>
git merge master
```


Ga naar de files kijken waar de verschillen zitten, en verwijder de HEAD en tekens waar nodig.

```
git add <filename>
git push origin <BranchName>
```

## How to change your bash profile:

First dive into your directory and add following lines to `vi ~/.bash_profile`:
```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```

Next change your source with the following command `source ~/.bash_profile`

Now you'll notice some beautiful colors are added in your terminal!
