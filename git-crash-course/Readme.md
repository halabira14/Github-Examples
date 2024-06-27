## Git Hidden Folder
There is a hidden foder called `.git`which tell you that our project is a git repo.

If we wanted to create a git repo in a new project, we create the folder and then initialize that repo using `git init`

```
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
git status
git add Readme.md
# makes changes to readme.md
git commit -m "add readme file
```

## Cloning

We can clone three ways: HTTPS, SSH, Github CLI

Since we are using GitHub Codespaces we'll create a temporary directory in our workspace

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

### HTTPS

```sh
git clone https://github.com/brianmaglunob/Github-Examples.git
cd Github-Examples
```

> You'll need to generate a Personal Access Token (PAT)
https://github.com/settings/tokens

You will use the PAT as your password when you login

- Give it access to Contents for Commits

### SSH

```ssh
git clone git@github.com:brianmaglunob/Github-Examples.git
cd GitHub-Examples
```

We will need to create our own SSH key pair

```ssh
ssh-keygen -t rsa
```

For WSL users and if you create a non default key, you might need to add it

```sh
eval `ssh-agent`
ssh-add ~/.ssh/alt-github_id_rsa
```

We can test our connection here:
```
ssh -T git@github.com
```

### Github CLI

Install the CLI

eg. Linux (Ubuntu)
```sh
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
&& sudo mkdir -p -m 755 /etc/apt/keyrings \
&& wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```

```
gh auth login
gh repo clone brianmaglunob/Github-Examples

## Commits

When we want to commit code, we can write git commit which will open up the commit edit message in the editor of choice.

```sh
git commit
```

Make a commit message without opening editor
```sh
git commit -m "add another exclamation"
```

Set the global editor
```
git config --global core.editor emacs
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

## Stashing

## Merging

## Add

When we want to stage changes that will be included in the commit
We can use the . to add all possible files.

```
git add Readme.md
```

## Reset

Reset allows you to move Staged changes to be unstaged.
This is useful when you to revert all files not to be commited

```
git add.
git reset
```

> git reset will revert a git add .

## Status

git status shows you what files will or will not be commited.

```
git status
```

## Git config file

The git config file is what stores your global configuration for git such as email, name, editor and more.

Showing the contents of our .gitconfig file
```
git config --list
```

When you first install Git on a machine, you are suppose to set up your name and email.

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