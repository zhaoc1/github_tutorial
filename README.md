# Github Tutorial
### Bushman Lab Code Review, Dec 14, 2016

## Introduction

Contributing to a project on Github gives you the chance to get involved with a project's development, help the developers, and get your issues and bugs resolved faster. It also helps further open source software, which powers most of the academic software we use here. Also it's fun. 

The instructions below will get you started on the basics of contributing to an existing software project.

### 00. Set up your SSH keys

Follow the instructions [here](https://help.github.com/articles/generating-an-ssh-key/) to set up SSH with Github. It's worth the effort and makes it so you don't have to always type your username and password on the command line. I would recommend doing it from the computer you'll be developing on, usually one of our servers.

### 01. Forking an existing directory

"Forking" a repository creates your own copy of the repository under your username. 

Navigate to https://github.com/eclarke/github_tutorial and click on the "Fork" button. Now you have your very own copy of this code under `https://github.com/<yourname>/github_tutorial`. 

### 02. Downloading your repository

You can download any public repository on Github. To freely make changes to a repository, though, you need to be an owner or collaborator of the repository. You are the owner of your fork of this repository though, so let's go ahead and download your copy to your computer. Type (do not copy and paste) the following command, substituting your username for `<yourname>`:

If you set up your SSH keys in step 00:

```
git clone git@github.com:<yourname>/github_tutorial
```

If you did not set up your SSH keys:

```
git clone https://github.com/<yourname>/github_tutorial
```

### 03. Making some changes

Right now your code exists in three places: 

1. The copy of your repository on Github is referred to as the `origin`.
2. The copy of your repo on your computer is your `local` copy.
3. The original repo you forked from is called `upstream`.

(To make it complicated, each of these repositories has "branches". Branches are effectively internal forks of your code within one repository. The original branch is usually called "master", and you can choose any name you want for other branches. We'll cover branching more later.)

When you make changes to the project on your computer, you'll be modifying your local copy. Let's add a new file with our name and a message.

On your terminal, type:

```
cd github_tutorial
nano <yourname>.txt
```

Type whatever you want in this file. Then press `Ctrl-X` to save it and quit.

Once you've saved these changes, go ahead and type `git status` to see what's up with your local repository. You'll see that the new file is in the "Untracked files" category. That means git is not paying attention to what changes in this file, and it isn't considered to be part of your repository yet.

To add this file, type `git add <yourname>.txt`. Type `git status` again. You'll see now that there's a change to be committed: you've added this file. 

Committing writes the changes into the "log" git keeps about your repository. You can go back to any commit and see what your repository looked like at that stage. This means that nothing is ever lost: if you accidentally delete or break some stuff and commit it, you can always go back to the previous commit.

Let's commit our changes now: type `git commit -m 'added a new file'`. The message you type after `-m` should succinctly summarize your changes, enough that when you look back on it you'll be able to remember what you were talking about. Commit messages are required, and it's recommended to always make them useful. 

### 04. Pushing to origin

You have now made a new file, added it to your local repo, and committed it. Your remote origin repo, the one that lives on Github, has no idea about these changes. It is up to you to "push" these changes back to it. It's very easy:

```
git push
```

Let's visit your repo on Github now. You should see your new text file there.

### 05. Issuing a pull request

Good job, you've altered two of the three copies of this repository. Sometimes it might be enough to stop there: maybe your changes aren't ones other people care about, or they're just for your own amusement.

Sometimes though, they're useful bugfixes or improvements that you want to share with the original developers upstream. To do this, you can ask them to "pull" your changes into their repository. This is called making a pull request.

You "pull" changes from a remote repository into yours. You "push" changes from a local repository to a remote one.

On your repo's page in Github, click "Make a pull request". Github knows where you got this fork from, and assumes that's who you want to pull your changes. Review the changes that are included in this pull request: it should just be your new file. Go ahead and click "Create pull request".
