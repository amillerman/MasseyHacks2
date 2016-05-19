#### Credit to [MasseyHacks](https://github.com/MasseyHacks/tutorials/tree/master/git-and-github) for the original and much of the current content.

# What is Git and where do I get it?

Have you ever thought about programming on a team? How will you all work on the same code without messing each other up? How will you keep the same code updated amongst everyone on the team? And what happens if you need to roll back some of your code to an older version?

**Git repositories** were invented for these purposes. Git is a **control system** that helps you manage your code, from working on the same code with a team to managing different versions and revisions of your code. The repository is where your project files will be stored, which can be code files, images, word documents, and any other files that may be relevant to the project. In fact, this guide is stored in its very own repository, that's how we're making it publicly accessible to you right now! Cool, eh?

**GitHub** is a website that uses this control system, and we will be using it to store our code. There is a free version, which requires your code to be visible to the public, and there's a paid version that allows you to have private repositories - we will be using the free version for this workshop.

If you plan to do any coding with your friends or colleagues, whether it's in the industry or just for fun, you'll probably end up using git repositories in some capacity. It's a very useful tool, and something every programmer should have experience using, so let's get started.

This workshop is not meant to be an all encompassing course on Git and GitHub. Instead, this will teach you just what you need to know about the two to be able to work in a group effectively during this hackathon, while hopefully gaining an understanding of the core concepts behind using a git repository.

## What programs do we use

1. You're going to need a GitHub account. Register one by visiting [github.com](https://github.com)
2. Get yourself a copy of GitHub Desktop: A friendly GUI version of a interfacing with your repository
		- [Download GitHub Desktop for Windows/OSX](https://desktop.github.com/)
			- Once you've downloaded it, be sure to run it and login using your GitHub account information
		- Linux not supported, sorry. If you're a Linux user, chances are you're going to want to opt for a command line tool such as [Git SCM](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
		
# Creating a repository and what to do with it

We're going to go through the process of creating our first `hello-world` repository, and then talk about how we're going to use it, so let's get started.

### Creating a Repository on GitHub

Let's get the online repository up and running first. Head over to your web browser go to [GitHub's Website](https://github.com).

1. After you've logged in, in the upper right corner next to your username, click the **+** and then click **New repository**
2. Name your repository `hello-world`
3. Write a short description, if you'd like
4. Make sure the **Initialize this repository with a README** option is checked off
5. You're ready! Click the big green `Create repository` button

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-new-repo-screen.png"/></p>


### Cloning a Repository on GitHub Desktop

Now that you have your online repository up and running, you've got to make a **local copy** of it by **cloning** it. Let's go over a brief rundown of what that means. 

We want our project files to be stored online on GitHub's servers, so everyone in the group can access the same code and so GitHub can handle all of our changes. But, in order to work with the files you've got posted on GitHub, you're going to need a copy of them locally on your computer. To do this, you clone the repository to your computer using GitHub Desktop, which will **pull** the content from the server to your computer. This way, the program knows where the code came from (your online repository), and after you have made some changes to the files and folders in the project, you will be able to use GitHub Desktop to **push** those changes up to the server so everyone in the group can access those changes. 

So this means there's going to be a version of the repository files online (on GitHub's servers) and a version on your computer. You're going to be aiming to keep the two versions synchronized; when you make changes to some of the files locally, you're going to need to **commit** and push those changes to the online version. Likewise, if someone else in your group pushes changes to the server, you're going to want to pull those changes to your local version, so you can work with what your group members have added or changed.

I really can't stress how important it is to understand this push/pull relationship between your local copy of the repository and the version that lives online, on GitHub's servers, so let's go over what these words mean again:
		- Pushing is what happens when you commit your changes from your local copy of the repository up to the online server
		- Pulling is what happens you retrieve (in GitHub Desktop, they also call it syncing) changes from the online server down to your local copy of the repository.
		
Push up, pull down, sounds simple enough right? We'll go over some of the problems you may encounter later, but for now let's get to cloning our repository and creating out local copy.

- Desktop Users (Windows/Mac):
	1. This step shouldn't be necessary if you logged in after first instaling the program, but in case something went wrong there, let's cover it here:
		 - In the upper right hand corner of the program, click the ![](https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-gear.png) icon and go to "Options":
			<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-choose-options.png"/></p>
		 -  Go to **Accounts** and click **Add account**
		 -  Under **Log in** fill in your username and password for GitHub and click **Log in**
	
	2. Now that you're logged in, click the encircled **+** icon in the top left. This will open a menu that will allow to "Add" a pre-existing repository, "Create" a completely new repository, or "Clone" a repository that you have on github.com
		<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-add-repo-menu.png"/></p>
	3. We want to "Clone" the repository we made on GitHub, so click the "Clone" button at the top
		- A list of all the repositories linked to your GitHub account will be listed
		- Select your `hello-world` repository
	4. Click the check mark at the bottom of the dropdown menu
		- This will bring up a dialog box asking where to put the repository
		- Choose the directory you want to put it in (or create a new one), then press "Ok"
		- The window should now look like this:
		<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-hello-world-repo.png"/></p>

### Important Note: 

At the top right, there will be two circles, one small and solid, one large and hollow. These are basically a timeline of the changes the repository has gone through. The solid dots represent commits that happened in the past and the hollow circle represents the current state of your local repository. For example, if you select that first solid dot, you will see the initial commit you made when first creating the repository, where you created that readme file. If you have the hollow circle selected, you will see what files and folders you have added, removed or changed in your local copy of the repository since you last synced with the server. We'll talk more about this in a moment.

- Terminal Users (Linux):
	1. Navigate or create a directory, using the terminal, that you'd like to keep your `hello-world` project in. While within the directory, call `git init`. This command will automagically set up the directory for use with git.
	2. Now we've got to tell git where the GitHub repository exists. Back in GitHub, make your way to the `hello-world` repo page, and copy the link that's given in the top toolbar. This is a link to this GitHub repository. I've selected the link in red for you so you can find it quickly in the image below.
		<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-repo-page-link-selected-scaled.png"/></p>
	3. Back in the terminal, call the command `git remote add origin <link to repo>`. This tells the local git repo about the online GitHub repository.
	4. Now let's get the two repositories in sync. The online repo has a `README.md` file. Clone it on the local repo by calling `git pull origin master`. Don't bother with `origin` or `master` for now.
        
Yay, you've cloned your first repository! Great job, now let's start looking at what we just did.

Fun fact: The online GitHub repositories search for a file called `README.md` and display it on the repositories web page. This is a great place to store information you want read when users first visit your repository. This entire guide is written in one of these readme files!

When you were creating your `hello-world` repository, you opted for a `README` to be created for you. If you look at your webpage right now, you can see it in action as a giant box under the list of files in your repository, and it contains the description that you initially gave to the repository.

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-readme.png" /></p>

GitHub also supports Markdown editing with `README`'s. Normally, the filename is `README.md`. If you don't know what Markdown is, don't worry. Just treat the `README` as a regular text file.

# Pull merge, push, and merge conflicts, what do they mean?


#THIS IS AS FAR AS I'VE GOTTEN IN MY CHANGES SO FAR
---


Say you make a change to your local repository. Open up your favourite text editor (bonus points if it's Vim) and create a new text file in the repository. It can be anything you want, and you can put whatever you'd like in it.

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-wowow-2.gif" alt="wowowowowwowowowowowowow"/></p>

This new file is going to represent a change to your code project. Now, lets get this change from your local git repo to the online official GitHub repo.

### Adding a File:

Git doesn't recognise new files unless you want it to. First, you'll need to tell Git that the file has been changed.

**Terminal users**: Use the command `git add` to add the file. There are lots of options to choose from:
	- `git add <filename>`: Adds the given file and nothing else.
	- `git add *`: Adds all the files in the current directory.
	- `git add .`: Adds all the files in the current directory recursively. That means that, for a folder that is sitting within your directory, all the files and folders within that folder will be added too.

**Desktop users**:  GitHub Desktop makes your job much easier by automatically detecting which files have been changed or added and providing you a graphical interface for chooising which ones you want to keep:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-changes-made.png"/></p>

Pressing the ![](https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-checkmark.png) next to a file will change whether or not git will include the changes when you go to *commit* (later on). You can even click on the file to show you what changes were made:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-show-changes.png"/></p>

### Committing a Change

Now you're going to have to tell Git that you'd like to officially record the changes in the repo. Whenever we tell git about the changes we've made to the project, we call it a commit. **You can add multiple changes in multiple files in just one commit** -- for example, I can create a hundred files in the directory and call a single commit. Git will figure it all out and list those hundred files as one change to the repo.

**Terminators**: committing is one simple command that you can run wherever in the directory. Call `git commit -m "<message>"`, where `<message>` is something to describe the changes that you've made in this change to the project. Trust me, you're going to want to describe your commits well.

**Desktopians**: In the main window, once you've chosen which files you want to include in the commit by checkmarking them in the list above, go to the lower panel and add a description and a summary, then press "Commit to master".

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-committing.png"</p>

### PUSH!

Now we're going to make the changes that you've made to your local git repo official, by pushing them to the official online GitHub repo. Under the hood, git tells GitHub about all of the commits that you've made on your local repo, and GitHub makes the same commits on the official repository. Even though you're pushing only one commit for now, keep in mind that **you can commit multiple times before a push**, and all of those commits will make it to the GitHub repo.

**Termies**, make the call `git push origin master`. From before, you should interpret this command as pushing everything at `master`, the local git repo, to `origin`, the online official GitHub repo. You'll have to provide your GitHub username and password for security.

**Deskies**, pushing is really easy for GitHub Desktop. Just press the `Sync` button in the top-left corner of the "History" tab. It looks like this:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-syncing.png"</p>

It should be noted that this doesn't just *push* your changes to GitHub, it also *pulls*. *Pulling* is the reverse of push: it takes whatever changes are on the GitHub repo and applies them to your local repo. This is useful when someone else makes changes to your repo on GitHub that you don't have, but more on that in a later section.

### Wowow, it's in the cloud!

Now, if you navigate back to the GitHub repo webpage, you'll be able to see the new file that you created, or any changes that you made to existing files. Congratulations!  :tada:  You've just made your first `add`, `commit`, and `push`!

## Section 3: Rolling back the Repository to a Previous Commit

In hindsight, we've made some mistakes. `important-change.txt` was a permanent blemish on my career, and I'm sure whatever change that you've made to your repos were similarly deserving of regret. Let's reset the repo, to an earlier, more pristine time.

### Open the Commit History

Head to the GitHub page for your repo and click on the left most entry to the top bar, the button that says `X commits`. You'll end up with the commit list, a page that has entries like these:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-commit-list.png"/></p>

It should be just two commits: the initial commit that was made when you created the repo, and the commit that you made when you made a change back in Section 2.

Each entry contains information on the user that made the commit, the message that was given for the commit, the time it was made, and some weird mish-mash of letters and numbers on the right. That mish-mash is what's known as a commit id, a string that uniquely identifies this certain commit. It's actually a small prefix of an SHA hash and, if you click on the clipboard to the left, you can get the full hash that identifies this commit. For me, `0747e2` was actually `07047e2b04c85b9fe3609f7b91558732e3c663ed`.

### Reverting to a Better Time

The commit where I added `important-change.txt` had an id of `07047e2`. Let's undo that mistake. Copy the shortened id of the commit that you want to move back to. In this case, it's the very first commit: `6a800ef`.

**Terminal users**, call the command `git reset --hard <commit id>`. Afterwards, call `git push -f origin master`. The `-f` tag tells `git push` to forcibly push it. Git is smart: it realises that the current state of the repo is the same as one of a previous commit, and won't push to be efficient.

**Desktop users**, you have two options. Right after you commit, you can press "Undo" in the bottom-left corner of the window right after you commit:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-undo-last-commit.png"</p>

or you can press the `revert` button on the commit page:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-desktop-revert.png"</p>

Both ways do the same thing.

Now go back to the official GitHub repo page and refresh. Look at the commit history now. The last commit you made is all gone. In practice, all of the commits between the last commit to the repo and the commit that you reverted back to will be **irreversibly erased**. You cannot revert this action.

### This is not the only way

Actually, in my opinion, it's a pretty bad way to do it. If this workshop had more time, I would be teaching you `git checkout` or `git reset --soft`. However, both commands require knowledge of branches or commit trees, something that overall isn't that important to using git when it comes to using it within a small team for a hackathon. If you have some time, I'd definitely recommend learning more into it. Just Google!

## Section 4: Collaboration!

The whole point of git and GitHub is being able to collaborate on a project with some teammates. Now you know how to work the two alone, it's time to learn how to work with friends -- or, more specifically, collaborators.

At this point in time, I'm going to ask you guys to split into pairs in order to simulate working teams. If you're reading this alone, grab a friend or pretend you have one.

### Adding a Collaborator

On your GitHub repo page, head over to `Settings`. You might have to type in your password at this point. Afterwards, on the left hand panel, click `Collaborators`. You'll end up at a page like this:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-collaborator-screen.png" /></p>

This is where you can add collaborators to a repo. A collaborator is a GitHub user that has read and write permissions on your repo -- that is, he or she is able to push their own changes to your repo. As such, they have complete control what goes on it. Go ahead and add your friend as a collaborator onto your account.

Any collaborator can now add, commit, and push freely to the repo as much as he or she wishes! As long as they follow the steps from a couple of sections ago and clone it to a local repository.

### Merging

Let's see this in action. Within the directory, have one person in the pair create a file `a.txt`, and the other person create a file `b.txt`. Make sure that the user that is creating `b.txt` is using terminal git. If both people wihtin your pair use GitHub Desktop, it's fine to have a Desktop user create `b.txt`. Let the person who created `a.txt` add, commit, and push first. They should be able to do so without any trouble, and, if you refresh the repo webpage, you should be able to see `a.txt` within the list of files.

Now, after `a.txt` is pushed to the respository, let the person with `b.txt` push his or her commits. However, if the second collaborator is using command line git:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-must-pull.gif" /></p>

The attempt to push `b.txt` will be rejected! Here's the rejection message:

```
To git@github.com:awolawol/hello-world.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'git@github.com:awolawol/hello-world.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

In simple English, this error message states that the problem git has is that the second user's repo is behind the actual official repo. He or she does not have all of the commits that the official repo has, as the first user added a new one when pushing `a.txt`. The second user's git repo has no knowledge of that commit, until now.

In order to fix this error, the second user must get all of those new commits from the online official repo to their local repo. Do this by calling the command `git pull origin master`. This command will take all of the new commits from the offical online repo and **merge** them with your current repository. For now, the only merge is to add the new `a.txt` created by the first user.

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-pulling.gif" /></p>

When calling `git pull`, you will be prompted with a Vim process to comment on what you've done in this merge and why you did it. If you're familiar with Vim, great! Say some words on what you've done. Otherwise, close Vim with `:q`, and the pull will finish. Near the end, after calling `ls`, you can see the `a.txt` appear in my directory.

### Merge Conflicts

Okay, this is pretty dangerous. Say if two people are both collaborators on one repository, and both of them edit the same file and push at the same time? Which change stays on the file? This is called a merge conflict.

Let's see what happens by purposefully creating one! Have both people in your pair edit README.txt at the same time. Let one person add, commit, and push first. They should be able to do so successfully. But, when the second person tries to push his or her commits to the official repository, it will be rejected, like in the last step, where we talked about merging. However, a simple `git pull`, for command line users, or `Sync`, for Desktop users, won't fix this problem.

This will happen to command line users:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-conflict-pull-2.gif" /></p>

Desktop users: after clicking on the `Sync` button, the program should tell you that it cannot merge the changes.

This specifically is called an **edit collision**: when two users change the same part of the same file, and GitHub doesn't know which edit to accept. How does git fix this? Git let's you decide.

Read the error message from `git pull` carefully:

```
Enter passphrase for key '/home/jeffrey/.ssh/id_rsa': 
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From github.com:awolawol/hello-world
 * branch            master     -> FETCH_HEAD
   2aa6655..a60bbc9  master     -> origin/master
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

The line `CONFLICT (content): Merge conflict in README.md` states the existence of the merge conflict, and that the `Automatic merge failed; fix conflicts and then commit the result`. In simple English, git is telling you that it tried to merge, but it couldn't, due to a conflict in `README.md`. Git then tells you to go and fix it yourself, and commit it afterwards.

Well, how does the `README.md` look like right now? Open it up and see! Desktop users should start editing within the GUI. Terminal users will have to navigate to the file within the directory and edit it with their own tools. When you open `README.md`, you should see something like this:

```
# hello-world
this is the repo description

<<<<<<< HEAD
this line was added to README.md by the second user but pushed after the last line was pushed, causing a merge conflict
=======
this line wase commited by the first user and pushed successfully.
>>>>>>> a60bbc9b01a8d7cd9cea9c20986db983f4279982
```

See the `>>>>>>>` and the `<<<<<<<`? Those two markers section off a part of the file to denote where the merge conflict exists: right in the middle of it. There is a separating `=======` in the middle. Above the `=======`, you have the changes to the file that second user was trying to add. Under the `=======` are the changes that the first user made to the file before the second user committed.

Git was kind enough to mark the merge conflict for us. Now, all that's left is to, as git told us, `fix conflicts and then commit the result`. So, using the conflict marks that git provides for you, manually go through the file and edit it to a final version that you want to be on the official repo.

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-conflict-fix.gif" /></p>

The merge conflict should resolve, and your changes will push successfully, with this new file as the final file on the offical repo!

If you don't want to deal with merge conflicts, just don't have multiple people working on the same file at the same time.

## Section 5: That's it!

That's all I have to teach you. Both git and GitHub are crucial tools in the industry, and, if you're going to Software Engineering as a career, these two tools will probably be taught within the first few weeks. There's a lot more depth to both git and GitHub that I have completely ignored in this tutorial in order to teach you all that you need to know for this hackathon within an hour.

You're off on your own for now! Feel free to come back to this tutorial if you're confused on a topic or there's something that you've forgot. Here are some commonly asked questions:

### Hey, I came back to this tutorial but it's not telling me what I need to know.

Google and StackOverflow! Seriously, pretty much all of the programmers that organised MasseyHacks are self-taught and learned through continuously searching Google and reading free guids on the Internet. Let's say I wanted to figure out how to make a copy of a repository:

<p align="center"><img src="https://github.com/MasseyHacks/tutorials/blob/master/git-and-github/resources/github-google-is-god.gif" /></p>

### What more can I learn?

Again, this tutorial is barely scratching the surface. We did not discuss branches, forks, cloning, tagging, and so much more. If you're looking to learn more about Git and GitHub, here are some helpful links:

 - Here's a great simple reference guide for command line users: [git - the simple guide](https://rogerdudler.github.io/git-guide/).
 - [Atlassian Git Guru Guides](https://www.atlassian.com/git/tutorials/) are really indepth and thorough. Definitely use this to go indepth for git.
 - There is a [GitHub Desktop Documentation](https://help.github.com/desktop/), but honestly, it kind of sucks. We've already taught you most of what you need for Desktop, and it's pretty simple and intuitive to use in the first place. The rest of the complexity can be found in the Atlassian tutorial.

Congratulations! :tada: You've made it out alive! Now you know how to use the basics of Git and GitHub. I hope you enjoyed learning from this tutorial as much as I did writing it. [@descrip](https://github.com/descrip)
