## Git Hidden Folder

There is a hidden folder called ".git" which tells you that our project is a git repo.

If we wanted to create a git repo in a new project we create the folder and the initialize that repo using "git init"

```
mkdir /workspaces/Zain-Github-Examples/new-project
cd /workspaces/Zain-Github-Examples/new-project
git init
touch Readme.md
code Readme.md
git status
#git add all
git add Readme.md
git status

#make changes to readme.md
git commit -a -m "add readme file"
```

## Cloning

We can clone three ways HTTPS, SSH, Github CLI

Since we are using GitHub Codespaces we'll a create temporary directory in our workspace

```sh
mkdir /workspaces/Zain-Github-Examples
cd /workspaces/Zain-Github-Examples
```


## HTTPS

```sh
git clone https://github.com/ZainVey/Zain-Github-Examples.git
cd Github-Examples
```
>You'll need ti generate a Personal Access Token (PAT)
https://github.com/settings/tokens

You will use the PAT as your password when you login

-Give it access to Contents for Commits

## SSH

```
git clone git@github.com:ZainVey/Zain-Github-Examples.git
cd GitHub-Examples
```

We will need to create our own SSH rsa key pair

```
sshe-keygen -t rsa
```
For WSL users and if you crete a non default key you might need to add it

```
eval `ssh-agent`
ssh-add /home/andrew/.ssh/alt-github_id_rsa
```

We can test our connection here:

```
ssh -T git@github.com
```

## Github CLI
Install the CLI

eg. Linux (Ubuntu)

```
type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
gh auth login
gh repo clone ZainVey/Zain-Github-Examples
```

## Commits

When we want to commit code we can write "git commit" which will open
up the commit edit message in the editor of choice.

```
git commit
```
Set the global editor
```
git config --global core.editor emacs
```
Make a commit and commit message without opening an editor
```sh
git commit - " add another exclamation"
```
## Branches

List of branches

```
git branch
```

Create a new branch

```
git branch branch-name
```

Checkout the branch

```
git checkout dev
```

## Remotes

We can add remote but often you will just add remote via upsteam when adding a branch

```
git remote add ...
git branch -u origin new-feature
```

## Stashing

## Merging

```
git checkout dev
git merge main
```

## Add

When we want to stage changes that will be included in the commit 
we can use the "."(period) to add all possible files

```
git add Readme.md
git add .
```

## Reset

Reset allows you to move staged changes to be unstaged.
This is useful when you wan to revert all files not to be commited

```
git add .
git reset
```
>"git reset" will revert a "git add ."

## Status

Git status shows you what files will or will not be commited

```
git status
```

## Gitconfig file

the gitconfig file is what stores yopur global configuration for git such as 
email, name, editor and more.

Showing the contents of our .gitconfig file
```
git config --list
```

when you first install Git on a machine you are suppose to set up your name
and email

```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Log

git log will show recent git commits to the git tree

## Push

When we want to push a repo to our remote origin

```
git push
```