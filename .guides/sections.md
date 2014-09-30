---
title: A POETIC INTRODUCTION TO GIT
files: []
editable: true
layout: 2-panels-tree

---
#Module 2 - Remote Repositories

This module comes with some files already created so you are ready to get down to business immediately.


##GitHub
GitHub is a platform that stores and manages remote repositories. 

As we will soon see, you can ‘push’ your local Git repo onto GitHub whenever you like. It is amazingly fast and there are many benefits to doing this, not least of which is that you have a remote backup of your entire project history, including commit snapshots. 

Being able to collaborate with other developers on the exact same code base is also a pretty big deal.

##Create a GitHub Account and an empty repository
The first thing you should do is to create a GitHub account. Watch the video below to see how to do this and also set up a new, empty repo ready to push your code into.

![640x480](http://www.youtube.com/watch?v=phzfEqEIt3g&feature=youtu.be)

Make sure you have the GitHub repo URL copied to the clipboard, which was the last step in the above video. It should look something like this

```
https://github.com/fmayx/mynewrepo.git
```

You should also have ready the GitHub user name and password that used for your GitHub account signup.

---
title: Setting up a Remote
files: []
editable: true
layout: ""

---
Make sure you have your Codio project in front of you. 

The first thing we need to do is to tell Git where the remote repo is located. You should already have the remote repo URL copied onto the clipboard (done in the last section) and you’ll be adding this as the last parameter you will enter into the Terminal as shown below (you may need to scroll to the right to see the whole line).

`git remote add origin https://github.com/your-gituhub-user-name/your-remote.git`

Let’s analyse this command

- `git remote add` tells Git to associate our project with a new remote repository
- `origin` is the name you decided to give to this remote repo. `origin` is the name most people use for the primary remote repo
- `https://github.com/your-gituhub-user-name/your-remote.git` is the URL of that repo. You get this from within GitHub as shown in the video (the bit you copied to the clipboard).

You can check the remote details at any time using

```
git remote -v
```
---
title: "Add some files, make some changes"
files: []
editable: true
layout: ""

---
So you feel that you did something with this project make some changes to your project. 

Add a new file and edit the contents of any of the files.

Once you’re done, you can stage and commit with 

```
git add -A (stage all tracked and untracked files)
git commit -am 'a few of my own changes' (to commit)
```

---
title: "'Pushing' to the remote"
files: []
editable: true
layout: ""

---
Now, we‘re ready do push our local repo to the remote Github repo. 

If you type 

```
git log
```

you can see that there are already a couple of commits in our repo all ready to push.

So, let’s push

```
git push -u origin master
```

- `-u` tells Git that the named remote (the next parameter 'origin') is the ‘upstream’ remote and so after this initial command, just using `git push` on its own is all that is needed, without having to type the full command above
- `origin` is the name of the remote that you want to push to and was defined in the previous section with `git remote add origin remote-url`
- `master` is the name of the branch (branches will be discussed in the next module) that you want to push

You will be prompted to enter your GitHub user name and password. Once you have done this, your local repo will be pushed to the remote repo.

Back on your GitHub page, refresh the repo you created there and you’ll see your files. You can drill down into the files and explore. 

![](.guides/img/git-explore.png)

That’s pretty cool. You now have a remote backup of your repo and, if it’s a public GitHub repo, others can access your code, but that’s for another time.


---
title: Play
files: []
editable: false
layout: ""

---
Now make some more local changes using the same sequence we did earlier, so

add files, modify content etc.

```
git add -A  (to add all changes to the staging area)
git commit -m 'commit message' (to commit)
```

Once you’ve done a commit or two, push everything again using just 

```
git push
```

and refresh your GitHub repo page to see the changes.

Note that `git push` is all it takes to do your pushes as long as you used the `-u` switch in the `git push origin master -u ….` command.

Keep playing around with things until you are completely happy with the process. Don’t worry about messing things up. Just get really comfortable and allow yourself to make mistakes. If you want to go back to the beginning, you can do the following

- `git reset --hard HEAD` to get your local back to the initial state for this module
- delete your GitHub repo in GitHub repeat the setup process

---
title: "'Pulling' from the remote"
files: []
editable: false
layout: ""

---
Now we’ll do things the other way round and actually make some changes on the remote GitHub repo before pulling them into our local repo.

##Commit Changes
First of all, make sure you have committed your local changes and pushed them exactly as discussed in the previous section.

##Edit a file on GitHub
Next, go to your GitHub repo and edit a file there by clicking on a file and then pressing the edit button. Having made your edits, enter a short commit message and press the 'Commit Changes' button.

##Git Status
Now, back in your local repo, you can check `git status`, but this does not really help you. Your local repo does not know about remote changes.

##Pull in remote changes
So, let’s pull in remote changes now using

```
git pull
```

Now, any remote changes you made will appear in your local project.
---
title: Git Log
files: []
editable: false
layout: ""

---
The pull we did just created a new local commit. If you type

```
git log
```

you will see a history of all commits in the repo, including the one that was pulled in from the remote repo. We’ll talk more about `git log` in the next Module.
---
title: Creating a project from someone else’s GitHub repo
files: []
editable: false
layout: ""

---
As a final thing, it is really easy to create a project from someone else’s GitHub repo. So you’ve got something nice and simple to play with, go to this URL

```
https://github.com/fmay/git-video-overview
```

This is a very simple project that we used to put together the Video Overview. 

Create a brand new Codio project from the Codio projects screen by pressing the Create button. On the next screen, select the Git tab and paste in the GitHub project ‘Clone URL’. This is located on the GitHub page on the right hand side and looks like this. To save you the hassle, this is the URL to copy and paste into the ‘Clone a git repository’ field.

```
https://github.com/fmay/git-video-overview.git
```

Now you can see the code in the Codio IDE and can start playing with it.

You will be able to edit the code but you can’t push modifications back to GitHub because you won’t have permissions.
---
title: Conclusion
files: []
editable: false
layout: ""

---
There’s a lot more to working with remote repos, but we’ll leave it there for the time being and come back to look at more advanced examples another time.