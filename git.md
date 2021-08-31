# <a name="top"></a>Gitting Started with git

Remember, if you are unfamiliar with the command line on Mac OSX or linux, here's a handy [cheat sheet](http://cheatsheetworld.com/programming/unix-linux-cheat-sheet/).

We will be using the [GitHub](https://github.com) web service to
distribute course materials, including homework assignments, and to
keep track of your work - so you will need to be set up with `git` and
GitHub too.

* [Git and GitHub](#github)
* [Conda](#conda)
* [IPython Notebooks](#ipynb)

## <a name="github"></a>Git and GitHub


Git is a system for version control of files - it tracks changes, allows you to
coordinate development amongst a team, lets you maintain parallel versions of
the code for making changes, while keeping the original intact.

Git can run as a service on your own machine.

You are probably reading this file in a browser on the GitHub website.

If you are, the first thing you want to do is create a github account of your own

Github is an online service that will allow you to use version control with your repositories and store them remotely! You do not need Github to use git, but you do need git to use Github.

Linux machines should already have git installed (I don't know ANY distros that do not).
Mac OSX users may need [XCode Developer Tools](https://apps.apple.com/us/app/xcode/id497799835?mt=12)
You can also get git through the `conda` package manager. Skip to the [Conda](#conda) section of this guide.


### Forking a repo

A fork is a copy (a "clone") of a repository, within GitHub, that belongs to you.
It is not strictly necessary to fork the main course repo: if you don't plan to
suggest any changes to the material, you can just clone it directly as
described below. But if you want to make a fork, follow these directions.

On the other hand, it's good practice, so you should do it this way.

While viewing the GitHub repository that you want to fork, make sure you are
logged in, and you should see a button in the top righthand corner marked
"Fork".  Click this button.  Ta-daa!  You have your own copy of the repository,
hosted at GitHub.

In some circumstances, it seems that GitHub will automatically have you
`Watching` previous forks of the repo by others.  Go ahead and `Unwatch` them
if you want to avoid the associated notifications.

### Cloning a repo

To get a repo onto your local system, you need to clone it with the shell command
```bash
git clone <address>
```
Here, `<address>` is the git address of the remote repo (either the original or your fork), which will be something like `git@github.com:KIPAC/StatisticalMethods.git`. You can reveal this address by clicking the "Clone or download" button on the repo's GitHub page. Give this command a try.


```
git clone https://github.com/<your_username>/ast310_2021_Fall.git
e.g.:
git clone https://github.com/gnarayan/ast310_2021_Fall.git
```

Remember, you should *fork* my repo to your GitHub account and clone your fork.

### Commiting a change

Within the repo, there is a `homework/` folder. Create a subdirectory with your FirstnameLastname and create a file with some random text in it.
To push this change to github, the first thing you need to do is to add this change to your local index.

You do this with:

```
git add homework/FirstnameLastname/example.txt <adjust the path as needed>
```

If you want, you can check the status of your updates with 

```
git status
```

That change you just added is staged, but not "committed" to your local repository first.
You commit it with 

```
git commit
```
which will open up a text editor and let you enter a commit message to describe what you are changing.

Alternately,
```
git commit -m "some useful and descriptive message"
```

Finally, to push your change from your local machine to github, you need to:

```
git push origin master
```

If you forked your repo and you just setup your git account, it should prompt you for your username and password.
This is because you are not yet authorized to write to files on GitHub's computers. Entering a username and password over and over will get tiresome quickly. 

To enable them to let you in, you just have to give them your *public SSH key*. (This is all worth it, I promise: setting this up will allow you to push and pull without typing your GitHub password all the time.)

Go to the [SSH settings part of your GitHub profile](https://github.com/settings/ssh) and add a new key, pasting in the contents of your file (do "`more ~/.ssh/id_rsa.pub`". "Title" can be anything - I use "laptop".) If that file doesn't exist, you can make one with the command `ssh-keygen`. Now you should be able to interact with GitHub repositories via the command line.
