# Git training - The basics

## Creating a new branch

Go to the repository
Fork the original repository
Go to the fork in your own gitHub profile
Copy the link of the fork

```
git clone <link of fork>
git checkout -b <BranchName>
git add <filename>
git commit -m "Add comments of the changes"
```

In case of a merge conflict:
(Make sure the upstream is correct) 
```
git remote add upstream <link to the original repository>
git checkout master
git pull upstream master
git checkout <BranchName>
git merge master
```

Compare the files and check for differences. Delete the HEAD and markers where necessary.

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
