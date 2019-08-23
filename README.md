# sandbox
A testing repo for playing around

Follow the steps below to get started. If you are new to version control it may seem complicated. The first few steps are easier but if it gets really confusing just message on slack. I want to go over in-person how to do this as it can be much easier with some whiteboard drawings. Try to get at least a little way into the interactive tutorial. Note that this kind of knowledge will look *very* good to prospective employers!

Getting started:
1. Create an account!
1. Notify Jason with your account name and I'll add you to this organization
1. Github is completely open to the public for reading! To keep your email address private, see: https://help.github.com/en/articles/setting-your-commit-email-address
1. In general it is good to become at least somewhat familiar with the git command line interface. There's a nice interactive tutorial to learn a few basics of working with files and doing commits: https://learngitbranching.js.org
1. GUI clients: I personally don't find them too useful, but maybe you would. Take a look at these https://gitup.co/ (mac only) or https://git-fork.com/ (mac or windows)
1. Click the Fork button to make a fork (fancy name for copy) of this repo in your personal account
1. Clone the copy to your computer with `git clone https://github.com/<YOUR_ACCOUNT_NAME>/sandbox.git`
1. Make a feature branch (named however you want) `git checkout -b my_branch_name`
1. Tangental note. Become familiar with these status commands 
    - `git status` Use this one all the time, particularly before doing commits or after adding files
    - `git diff` Use before adding files to double check your changes (git will highlight in red/yellow potential problem areas)
    - `git branch -vv` This lists all existing branches and what remote they are tracking
    - `git remote -v` This lists all remotes, by default just the origin remote (read-only and read-write are listed seperatly)
10. Add a new file and commit it. `git commit -m "my brief description of changes"` The -m option is good timesaver!
1. Push your commit (and new branch) to your github fork `git push origin my_branch_name`
1. Create a pull request back to thebetadecays organization. Usually Github autodetects your push operation and you'll see a yellow bar with green button "Compare and Pull Request". Otherwise, just click the pull request link above the file listing and choose the correct repositories. You want to merge from your feature branch to the master branch of thebetadecays
1. You or another member of thebetadecays can merge the change into the org repo

You might be thinking, "what if other folks merged changes too after I made my fork? How do I get those changes in my copy?" Here is how to do it!
1. When you `git clone <repo>` a "remote" is automatically created for you, by default named "origin." Notice that was specified above when you did the `git push origin <branch_name` command. To get changes from other people, add a secondary remote called "main." `git remote add main https://github.com/thebetadecays/sandbox.git`
1. To fetch and merge those other changes do: `git checkout master` then `git pull main master`
1. Your local copy is now updated. Update your fork on github by simply `git push origin master`
1. The master branch is now up to date on both your copies. To update feature branches, first switch to a branch with `git checkout branch_name` then merge with `git merge master` and push the updated branch to your github `git push origin branch_name` Repeat for each branch as needed.

Takeaways:
 - In the above flow, realize that there are three distinct copies of the repository and it's files/directories
   - The main one in the thebetadecays organization on github
   - The forked copy in your personal account on github
   - The copy on your personal computer that you pulled from your personal account
 - Each of those copies has the "master" branch and zero or more feature branches
 - A pull request is used to merge changes from a branch in a forked copy on github to another branch (usually master) on the main org repo
 - Too many branches can make things really complex. In my experience, try to keep at maximum only 2-3 feature branches in addition to master
 - Likewise, try to keep branches short-lived. After a pull request has been merged, delete the branch! `git branch -D branch_name`

git is a powerful tool, there are many more operations but this little guide will serve most useage.
