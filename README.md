# Git Back Control of Your Code

## A Simple and Straightforward Workflow for Working with Git and Github

Becoming a better developer is about finding the process and workflow that works best for you and the rest of the team. I believe that version control is something all developers should use. Specifically, I think that git is a great option.

There can be a bit of a learning curve with version control, but once you start using it, it becomes essential.

If you are looking for a more interactive approach to learning git, then [give Try Git a shot](http://try.github.com/).

*This post is a follow-up to [a presentation I gave](http://www.gristmill.io/workshops/3-git-back-control-of-your-code-learning-how-to-manage-your-code-with-git-github) on using Git and Github. Going through [the slides](http://brettchalupa.github.com/git-presentation/) should give you a quick overview of what was covered. This post is meant to take it one step further for those who could not attend.*

## Why use version control?

The first question you are probably asking yourself is, "Why even use version control? I've got Dropbox! That's my version control." Getouttahere. Dropbox isn't version control. It's hosting for backups with somewhat deep OS integration. It's a good tool, but it's not a tool that should be used for managing your project's code.

Developers should be using version control because:

* Keeps a track-record of all of the changes you have ever made, ever
* Allows for collaboration with other developers without stepping on toes
* Provides a form of back-up by hosting a repository on another server, whether it is on the web or locally

It's essential to programming. Working in an environment without version control is terrifying.

## Why use git?

The next logic question is why use git? What about subversion or mercurial?

Use whatever fits your needs the best. Version control systems, IDEs, and code libraries are tools. They are supposed to make your life easier. Use what you are most comfortable with. Use the tool best for the job. Use whatever it is that will help you become a better developer. It's up to you.

Here are the reasons why I prefer to use git:

1. Github. This may be a strange reason, but Github is a reason why I use git.
2. The strong community and vast amount of resources.
3. The fact that [it is a distributed version control system](http://www.joelonsoftware.com/items/2010/03/17.html).

If git isn't for you or you prefer another type of version control, then that's totally fine.

## Why use Github?

There are a few options for git hosting out on the web. The two most common are probably [GitHub](http://github.com) and [Bitbucket](http://bitbucket.org). The two are very similar in terms of their features (Bitbucket also supports Mercurial, another distributed version control system). The major difference between the two is that Bitbucket allows for free private and public repositories. GitHub only allows for free public repositories. What this means is that if you want to host private projects on GitHub, then you need to pay money. If that's not for you or you can't afford it, then use Bitbucket. Most of this guide applies for use with Bitbucket or GitHub.

That being said, I prefer to use GitHub over Bitbucket because:

* Pull Requests - GitHub simply handles pull requests in a much nicer fashion, allowing people to comment on specific files in a commit or just on the pull request in general.
* The [help section](http://help.github.com) is super useful. It's well written, organized, and more than enough to get anyone going.
* [Gists](http://gist.github.com) - paste snippets of code publically or privately with features like comments and forking.

Moral of the story, try both out and see what works for you.

## Useful Terminal Commands

This guide should really be called *Using git and Github (with the terminal)*. That's the core of this guide - using the terminal. Whether it is msysgit on Windows or Terminal for Unix users, we will be using commands the entire time.

Beginning to use the terminal can be a daunting task. The nice thing is, there is only about a handful of commands you'll use daily. Once you get the hang of those, the workflow starts to make sense.

Here are a few of the most common commands you'll use when working with the terminal.

* `pwd` - print working directory a.k.a. where am I?
* `ls` - list files and directories in current directory a.k.a. what do we have here?
* `cd path/to/location` - change directory
* `touch path/to/file.rb` - create a file
* `mkdir path/to/directory` - create a directory
* `rm path/to/file.rb` - remove a specific file

### Flags

Flags are little extra magical parameters you can pass in with terminal commands. They're pretty useful, and as you explore and research, you will continue to discover more.

* `-a` - show all
* `ls -a` - show all files in the current directory, not hidden and hidden
* `git branch -a` - show all of the local and remote branches for the current git repository
* `-v` - show the current version of anything
* `ruby -v` - display the current version of Ruby installed
* `-h` or `--help` - list the flag options of the command you're running, when in doubt run -h

## Setting up git

[Follow this guide.](http://help.github.com/) That's it. Really. Github's guide on getting started with git on Windows, Mac, or Linux is precise and the best resource out there.

help.github.com will be your best friend while you learn to use git and Github (and even when you continue to use it).

## Adding to the Codebase

To start off, if you haven't already, you need to clone the project:

`git clone git@github.com:projectowner/project-name.git`

After the project is done cloning, change your directory to the project:

`cd project_name`

Once you've changed directories, you're almost ready to code. Next up is to make sure you're on the proper branch. To see what branch you are on, use the following:

`git branch`

If you're on master branch, there's probably a problem. You need to change branches or create a new one. Let's assume you need to create a new one. Please do the following command (where bc is your initials, this makes identifying who is working on what branch much easier):

`git branch bc/branch_name`

If you were to do

`git branch`

again, you'd see your new branch! To switch to that branch, simply do the following:

`git checkout bc/branch_name`

If you're feeling really snazzy, you can create a branch and switch to it at the same time by running:

`git checkout -b bc/branch_name`

Now you're ready to code! Once you're all done (or you think you're done), go ahead and add those changes. First, to see what changes have been made, simply do:

`git status`

You'll see any of the files you've added, changed, or removed. The most basic and quick command to add your changes to a commit is:

`git add .`

This will add of your new files and changes to the commit. To delete files, all you need to do is the following command:

`git rm file.rb`

If you delete your files a different way, you still need to run the command above to make git aware of the changes. If you erase a lot of files at once, here is a helpful command to make git aware of the changes:

`git add -u`

Once you've staged all of your changes to your commit, go ahead and make that commit!

`git commit -m "Your commit message!"`

Wow, great job! You're almost there. Next, all you need to do is push those commits to the remote repository on Github, and you're a git wizard.

`git push origin bc/branch_name`

## Merging Branches

You've created a branch, made some changes, saved those changes, and pushed them to your branch on the repository on Github. Now you think you're done coding your feature and you're ready to merge your branch into the master branch (or development branch depending on your structure). Now just hold your goddamned horses for a minute. Before you merge to master, you need to open a pull request. To do such a thing, navigate to your branch on the project in Github. Above all of the code on the upper-right, you will see a little button that says "Pull Request". Click that bad boy to open a pull request.

Once you've opened a pull request, everyone will be notified via email (if they have that setting on) and a Github notification. What happens next is out of your hands for a little while. At least one other programmer needs to go through your code and make sure it's up to snuff. Make sure it's properly commented, it makes sense, and there is no [code smell](http://en.wikipedia.org/wiki/Code_smell). If there are some problems, expect them to leave some comments where the problems lie. You need to go through the code, make your changes, commit those changes, and push them again.

How you and your team handle pull requests is up to you. In my opinion, it's best practice to have *at least* one other person review your code. Once they give you an _LGPA_ or a _Looks Good, Pull Away!_, you're ready to close & merge the Pull Request. Click the little button at the bottom of the pull request, and you're almost ready to start working on your next feature.

You've got to remember to clean up though. Switch to your development or master branch:

`git checkout master`

Now go ahead and delete your local branch:

`git branch -d bc/branch_name`

Next you've got to delete your branch on Github:

`git push origin :bc/branch_name`

A few last steps and you've merged your first feature into the codebase. You've got to pull from the master branch on Github to get the lastest changes from the Pull Request merge:

`git pull origin master`

Now you're done merging you're branch. You've cleaned up and got your latest changes from the merge. Start the whole process over from the beginning and code away.

*It's worth noting that this is probably a lazy approach to handling merges. [There's a ton of discussion on this topic and the proper ways to do it.](http://longair.net/blog/2009/04/16/git-fetch-and-merge/)*

## Other Useful git Commands

There is a lot more to git than what was covered in this document. As everyone uses tools more and more, there is a hope to continue to learn more about that tool. As I learn more, I will be updating this with other important git commands and concepts.

### Rebase

If you're on the branch `bc/current_working_branch` and you want to make sure you're not going to have merge commits, you'll want to rebase often.

First, run:

`git fetch origin master`

Then, run:

`git rebase origin/master`

This will put your commits on top of the latest `origin/master` commit. This will not update your local master branch, so be advised.

If you want to do an interactive rebase, it's the same process except that you say `git rebase -i origin/master`. I usually do a regular rebase before I do an interactive rebase so I can go ahead and fix any conflicts without the added confusion of an interactive rebase.

### Reset

If you mess up and want to go back a commit (or even more), simply do:

`git reset --hard HEAD~1`

The `HEAD~1` means ONE commit before head. If you wanted to do FOUR commits before the head, simply do `HEAD~4`

Or, you could look at the output of git log, find the commit id of the commit you want to back up to, and then do this:

`git reset --hard <sha1-commit-id>`

If you already pushed it, you will need to do a force push to get rid of it:

`git push origin HEAD --force`

### Stashing Changes

If you're ever working on code and need to store or **stash** your changes for later, there is a command for that. Run the following command to safely stash your changes in current branch away.

`git stash`

When you're ready to have those changes back, you can run:

`git stash pop`

Stashing is useful if two people are working on the same branch at the same time. If person A has made some code changes and person B has as well there may be some conflicts. Person A most likely wants to get the changes person B made, so if person A stashes their current changes and pulls from the branch then pops the stash, person A's changes will be reflected with person B's changes.

## Additional Resources

* [git Homepage](http://git-scm.com/)
* [git cheat sheet by TOWER](http://www.git-tower.com/files/cheatsheet/Git_Cheat_Sheet_grey.pdf)
* [Try Git](http://try.github.com/)