# HowToUseGit

This quick guide provides a basic stating point for working with git. For more information use google or follow the guide on https://rogerdudler.github.io/git-guide/. To learn git take a look at https://learngitbranching.js.org.

In general:
- Use git for everything that requires version tracking
- Do not use git for measurement data, videos, images, ... (that do not require versioning)
- Do not add versions to your filenames. Git will handle the versioning.

Our projects are stored inside git organizations on github. The organization we be created by us at the beginning of your project. You have to provide your github account name to be added the the `organization`. In each organization is a root repository with the same name as the organization. This root repository contains further repositories as `submodules`. Please add as many repositories as necessary to seperate logical project parts from each other.
Documentation on how to use each subproject should be done in the `README.md` file of each repo.

We encourage you to use git through your project development process and to take advantage of gits features.


## Create a ssh key pair

We need a ssh key pair for verification in github. The key pair can be shared between windows and WSL if necessary

### create ssh key in Windows using the command line
```
ssh-keygen
```
Just proceed with `Enter`. A password is not necessary.
To show the key again use (you may change the path to your file).
```
cat C:\Users\<USER>/.ssh/id_ed25519
```

### (optional) copy Windows ssh key into wsl environment

You can share the same ssh key between windows and wsl. To do so open wsl by typing:
```
wsl
```

In wsl:

```
cp -r /mnt/c/Users/<USER>/.ssh ~/.ssh
```
\<USER> must be replaced with your username

```
chmod 600 ~/.ssh/id_ed25519
```
if you have used a different name for your ssh key, change the file name in the command above.

## Creating a GitHub account

Create an account on
```
https://github.com/
```

### Adding your ssh key to github

This is necessary for every device!

1. Click on your Icon in the top right and select `Settings`

![Add SSH Key 1](https://github.com/CampusMinden-Projects/HowToUseGit/blob/main/images/add_ssh_key_1.png?raw=true)

2. Click on `SSH and GPG keys`

![Add SSH Key 2](https://github.com/CampusMinden-Projects/HowToUseGit/blob/main/images/add_ssh_key_2.png?raw=true)

3. Click on `New SSH Key`, past your generated ssh key and use a usefull `Title` for your SSH Key. For example "Work Laptop".

![Add SSH Key 4](https://github.com/CampusMinden-Projects/HowToUseGit/blob/main/images/add_ssh_key_4.png?raw=true)

## install git

Download the latest git version from
```
https://git-scm.com/install/
```
Click `next` through the whole installation.

## install Tortoise Git

Tortoise Git extends your windows context menu by usefull git tools. You can download it from
```
https://tortoisegit.org/download/
```
Click `next` through the whole installation and run the `first start wizard`.

In the `first start wizard`:
1. Set the language to `english`.
2. Set the Path to `C:\Program Files\Git\bin` (if you have not changed the installation path; otherwise fill in the right path).
3. Set your commit credentials. These are used to determine who added which code.
4. Set the SSH client to `OpenSSH`.

## Clone repository

Open the repos main page, click on Code and select SSH. Copy the URL.
![clone_repo.png](https://raw.githubusercontent.com/CampusMinden-Projects/HowToUseGit/refs/heads/main/images/clone_repo.png)

You are free to use Git Desktop, Git Bash, Tortoise Git or whatever.
For this document we use Tortoise Git. (see [install Tortoise Git](#install-tortoise-git)

1. open the folder you want to past the repo in and select git clone from the context menu.
![clone_repo_2.png](https://github.com/CampusMinden-Projects/HowToUseGit/blob/main/images/clone_repo_2.png?raw=true)

2. past the URL and click OK.
![clone_repo_3.png](https://github.com/CampusMinden-Projects/HowToUseGit/blob/main/images/clone_repo_3.png?raw=true)

3. The repo will be copied to you local system.
![clone_repo_4.png](https://github.com/CampusMinden-Projects/HowToUseGit/blob/main/images/clone_repo_4.png?raw=true)

## working with git

You can do any modifications you want in you local repo. (Although deleting the `.git` folder is not recommended)

### commiting changes

One you are at a point, where your changes are a `finished subproject` you can `commit` your changes using `git commit`. 
- Committed changes are still local. 
- You can decide, if you want to commit to the main branch, another branch or create a new one. (see [Branches](#branches))
- You must leave a short message, describing the changes in the current commit
- Select the files you want to include in the commit
![commit_1.png](https://github.com/CampusMinden-Projects/HowToUseGit/blob/main/images/commit_1.png?raw=true)

### push local commits

To upload your local commits, use git push.

### pull online changes

To get the online changes, use git pull.

### branches

Branches are use to develop different features in parallel without being dependent on other development processes. Use a dedicated branch for developing sub projects and merge the branch into the main branch when finished.

### .gitignore

The `.gitignore` file can be used to exclude files from being versioned. Use it!
For example `__pycache__` can generally be part of `.gitignore`. Tortoise git provides a context menu option for quickly adding files to `.gitignore`.

