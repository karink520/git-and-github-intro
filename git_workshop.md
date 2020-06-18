
## I. Start a new git repository (with Git `init`)

1. Create a directory (folder) that will contain the files for your project.
2. Navigate to that directory in the terminal.  (On Windows, you can use the Command Prompt or Git Bash).  To navigate use `cd` and `ls` if you are on Mac or Linux, `cd` and `dir` if you're on Windows.
3. Make a new file called `ReadMe.txt` and add some text to it (just a sentence is fine), and save it.
4. Type `git init` in the terminal; this will initialize the repository.
5.  Type `git add ReadMe.txt` to tell Git to start tracking the `ReadMe.txt` file and to include this file in the next commit.  (If you want, try entering `git status` before you do this step and then again afterwards to see what changes.) 
6. Make a first commit by typing: 
    `git commit -m "this is my first commit!`


### Alternatives:
**If you have an existing project and want to start using Git with it:**

In this case, navigate to the directory for the existing project with the Terminal.  Enter `git init` to create a new repository in this directory.

**If a collaborator just made you a (co)-owner of a repository on GitHub:**

With your web browser, navigate to the repository on your GitHub account.  Click "Clone or Download".  You should see a url show up that looks something like `https://github.com/user_name/repo_name.git`.  In your terminal, navigate to the directory where you would like to put the project that you just got added to. Then type into the terminal `git clone https://github.com/user_name/repo_name.git`, replacing the example url here with the one you see on GitHub.  You should now have a repository locally on your computer, and it is linked to the remote repository.  The remote repository be default has the short name `origin`.

**If you want to use someone else's existing repository on GitHub as a jumping off point:**

See part V on forking.

<div style="page-break-after: always;"></div>
<br>

## II. Connect your new repository to GitHub

1. Log in to GitHub.
2. Click "New Repository" in the upper left and fill out the form to give your repository a name.
3. Follow the instructions under "Push an  existing repository", which will ask you to enter some code back in the terminal/command line (something like):

    `git remote add origin https://github.com/username/new_repo`

    `git push -u origin master`

4. Check that the example file you made in part I should shows up in your account on GitHub!

You now have a local repository on your computer that is connected to a remote repository on GitHub.
In the above two lines, we convention by giving the remote repository the short name of origin (its longer name is something like `https://github.com/username/new_repo`, but we don't want to type that out all the time!). When you see `origin` throughout this workshop, you should be thinking about the repository living remotely, on GitHub, rather than locally, on your computer.

Note that we could have given it a different name instead of origin, and later on we'll see good reasons for a remote repository to have a different name.

<div style="page-break-after: always;"></div>

## III. Learn and practice a simple Git workflow (with with Git commands `fetch`, `merge`, `status`, `add`, `commit`, `push`)

1. We'll use the command `git fetch` to retrieve any changes from the remote repository, and store those changes locally for future use.
Since `fetch` just retrieves the changes and doesn't do anything with them, it's a very safe command to use; you won't accidentally delete anything by using it.  Type:

   `git fetch origin` 

   into the command line and read the message you get back.
   Note that we don't expect to see any changes in the remote repository relative to our local copy, because we just connected up the two!  But if we were working with 
   a collaborator, say, and they had changed what was on GitHub, then `fetch` would get their changes.

2. We'll use `git merge` to combine merge in any changes that you just fetched.  This means that if a collaborator changed some lines of code and put those changes on GitHub,
when you merge, you'd get there revised version on your computer. Type:

    `git merge origin/master`

    Note: we don't expect anyhing exciting to happen here, since our local repository already matched the remote reposity.  We're just practicing the basic workflow for now.
    Recall that `origin `refers to the remote repository up on GitHub.  `master` refers to the branch that we're on, but we'll learn about branches later on.

3. Make changes to your local repository.  This is where you're doing your coding, adding new features, and fixing features that need to be fixed!  To simulate that process for now, just make a small change by opening up `ReadMe.txt` and editting the text a bit.

4. a. The command `git status` is another safe, nondestructive command that you can use anytime you need a little more status information.  It will tell you the status of each file in
your local repository.  Files can be staged, unstaged, or untracked.  Staged files are set to be included in your next commit.  Unstaged files have changes that you've made since the last commit, but are not yet set to be included in the next commit.  Untracked files are will not be included in your commit, and git is not tracking changes in these files.  
The `git status` command will also tell you what branch you are on, which will be useful later when we learn what branches are and how to use them.
Type:

    `git status`

    And read the response you get.

    b. Make sure that any changes you have made and that you like get included in the next commit by using `git add` on each of the files that have changes. Type:

    `git add ReadMe.txt`

    where filename is something like `ReadMe.txt` or whatever you created in Part I.
    If you have more than one file you've changed (usually you do!) just use a  `git add` command on each separate file.  Once you're done, you can (optionally)
    use `git status` again to see that you successfully staged the file that has been updated.

    c. Do the commit.  This is making a checkpoint that you can roll back to in the future.  Since you staged all the files you changed, this commit will include all the most recent changes in your files. You'll also attach a descriptive message to the commit, which will help create a nice record ofr your work.
    Type:

    `git commit -m "Made my readme better, hooray!"`
    
    In general, replace the message in quotation marks with a message about what you did &mdash what bug did you fix, or what functionality did you add?

5. Repeat steps 3 and 4 a few times, making changes and committing those changes with a new message each time.  (This step is for practice with the workflow, but also to mimic what you willreally do with Git, where you are likely to make several commits locally before you arrive at something you would like to push back up to the remote repository.)

6. Now you'll want to include any changes that have been made to the remote repository while you were making your own changes (in this toy example, of course we'll be up to date, but in real life you might not know if a collaborator might have changed something while you were working).  We'll repeat steps 1-2.

    Type:

    `git fetch origin`

    Then type

    `git merge origin/master`

7. All of your committing just saved changes locally.  Now you need to send those changes off to the remote repository on GitHub (remember that the remote repository has the short name origin).  We'll send our changes off to the remote repository with the `git push` command.  Type:

    `git push origin master`

    If you go to your GitHub account in your web browser, you should now be able to see the most recent changes you made now included in your files.

8. If time permits, repeat steps 1-7 to practice the entire process again.

Great work! Take a moment to celebrate. If you are working by yourself or in a small team, that might be your entire workflow with Git and GitHub! If it seems like a lot at once,
post a reference to the commands somwhere handy and remember the overall flow: incorporate changes from the remote repository by using fetch and merge, make your changes and the commit them, using status, add, and commit, incorporate any additional changes from the remote repository with fetch and merge, and push your changes back to the remote repository. For reference, here's a concise list of the steps:

`git fetch origin`

`git merge origin/master`

(Edit your files)

`git status`

`git add name_of_edited_file`

`git add name_of_another_edited_file`

(etc., using the actual names of your files instead of name_of_edited_file or name_of_another_edited_file)

`git commit -m "include an informative message here"`

(Make more edits if desired)

`git status`

`git add name_of_edited_file`

`git add name_of_another_edited_file`

(etc., using the actual names of your files instead of name_of_edited_file or name_of_another_edited_file)

`git commit -m "include an informative message here"`

`git fetch origin`

`git merge origin/master`

`git push origin master`

### Alternatives:

The `pull` command combines fetching and merging into one command.  It is somewhat safer to fetch and merge separately, so that you can examine the changes that the fetch has retrieved before merging them.  Thus, fetching and merging separately is recommended.

In incorporating changes that have been fetched, and alternative to merging is rebasing.  Some people prefer to rebase because it preserves a linear history (look up git merge vs. rebase to learm more about this topic). If you prefer to rebase instead of merge, replace all the `git merge` statements in this document with `git rebase` (e.g. `git rebase origin/master` instead of `git merge origin/master`)

 <div style="page-break-after: always;"></div>
<br>

## IV. Dealing with merge conflicts.

Now let's suppose you are working with a collaborator. You both edit your local versions of the repository and pushing those changes to the remote repository. If you are working on different parts of the code, then merging in your collaborator's changes won't cause any problems: when you do `git fetch` and `git merge origin/master`, you will update your local files so that they include your collaborator's changes.  However, if you both have made changes to the same line of code, you will get what is called a **merge conflict** when you do the `git merge` step.  You will need to resolve the conflict before you continue. If you've tried a merge command and gota message that there was a merge commit, you can do the following.

1. Type `git status`, if you like, to see a little more information.  (Remember, `git status` is informative and doesn't change the state of anything).

2. In a text editor, open the file that has the merge conflict (or a file with a merge conflict, if there are several with conflicts).  In the file, at the line(s) of the merge conflict, you'll see something like:

```
<<<<<<< HEAD
This is the change you made
=======
This is the other version of this line.
>>>>>>> branch_name_you_are_merging

more content
```

The text between <<<< and >>>>>> is showing you both (conflicting!) versions of the line. The first part is the version in the current branch.  The second version, after the `======` comes from the branch you were trying to merge.  So if you had started the merge with `git merge origin/master`, you'd see your changes on the current branch above the `======`, and the changes that you retrieved from the master branch of your remote repository below the `======` (these would likely be changes from a collaborator).

3. Edit the file in the text editor so the conflicted line looks how you want it to be.  Maybe you keep one of the existing versions of the lie or maybe you replace them both with a mix of the two or something better. In the end, the file should look just how you want it to look going forward (with no more <<<< or ==== type extras!).  Save the file. If you have multiple conflicts and/or conflicts in multiple files, edit each conflicted line in this way.

4. Back in the terminal, `git add` the files where you resolved merge conflicts, as in:

    `git add ReadMe.txt`

5. Finish the merge by committing, with a message about what conflict you resolved and how.

    `git commit -m "merged and resolved conflict"`

    Then, the merge should be complete (and will have its own merge commit in the record), and you can proceed with whatever you wanted to do after the merge (e.g. pushing the now succesfully merged changes to the remote repository)




<div style="page-break-after: always;"></div>
<br>

## V. A workflow with branches and pull requests

As your project or your team gets larger, you may want to separate out work on different features of your project from the main project itself. You also might want to have someone review a team members committed changes before they get incorporated into the master branch of the remote repository. In general, using branches and pull requests promotes code quality by helping us avoid changing the master branch until we have something worthwhile and high quality to add. It also promotes collaboration by allowing space for collaborators to discuss before including one person's change into the master branch of the remote repository.

1. Retrieve and incorporate any changes from the remote repository with:

    `git fetch origin`

    `git merge origin/master`

    Resolve merge conflicts if necessary.

2. Create a new branch and move to it with the `git checkout` command (so that the work you do will be on that branch) by typing:

    `git checkout -b mybranchname`

    Instead of `mybranchname`, you can name the branch anything you like, just aim to keep it short and descriptive of the work you are planning to do on it (e.g. are you adding a certain feature or functionality to your code? are you fixing a bug?).  Note: if you were to to aready have an existing branch that you want to move to, you could omit the `-b` flag in the command above to just move to that branch, without creating a new one.

3. Make changes to your repository.

4. Check the status with:

    `git status`

5. Stage the files that you want to include in the commit with:

    `git add <filename>`

6. Commit the changes with:
    `git commit -m "informative message here"`

7. Repeat the previous four steps as desired, making and committing changes.

8. Retrieve and incorporate any changes from the remote repository with: 

    `git fetch origin`

    `git merge origin/master`

    Resolve merge conflicts if necessary.

9. Push your changes to the remote repository with:

    `git push -u origin mybranchname`

    This is a different way to use `pull` than we did earlier.  Before, we used `git push origin master` to push our changes directly to the master branch.  Now, we're being a little more cautious; we are still pushing our changes to the remote repository, but we're pushing not to the master branch but to a branch in the remote repository that corresponds to the local branch that you created in step 2.  (Note, the `-u` flag tells git to actually *create* this branch in the remote repository, linked with the local branch you created in step 2.)

10. If you think the changes you made on this branch and pushed to the remote repository are ready to be incorporated into the master branch, you can use GitHub ask the owners of the repository (you or teammates), to incorporate the changes from that branch into the master branch of the remote repository.  You'll do this with *pull request* on GitHub.

    Navigate to your GitHub account and the repository in your web browser.  In yellow, you'll see "your recently pushed branches:".  Click on "Compare & Pull" request in the top left to make the pull request, including a message to your project teammates when prompted.

11. At this step of the workflow, you and your team have various options for how to impose quality control for your code. A typical approach would be to wait for a teammate to review your changes and approv merging them into the master branch (your teammate might give feedback for you to respond to before merging).  The pull request allows the opportunity for a dialog between team members before including the changes that one person has made.  You can also use GitHub Actions to create automated checks that could including running tests that you create, or syntax checks, anytime someone creates a pull request.

    If you are an owner of the repository, you *can* approve and merge your own pull request.  For practice, use GitHub to approve and merge the pull request, and then delete the remote branch that you created in step 9.

12. **After your changes were successfully merged** into the master branch of remote repository, and you're all done with this branch, move back to the master branch locally with:
    
    `git checkout master`

    And then delete the local branch that you created in step 2 with:

    `git branch -d mybranchname`

    The `-d` flag indicates that you are deleting the branch.


13. Get the changes that you pushed and merged into the master branch of the remote repository into the master branch of your local repository with: 

    `git fetch origin`

    `git merge origin/master`


Great work!  Including Git branches and GitHub pull requests in your process takes a little more work, but it can pay real dividends by improving your collaboration and allowing you to include more checks to help maintain high quality code.

To add a collaborator to a repository on GitHub, you can navigate to the page for the repository and click 'Settings', which is the rightmost tab.  Select "Manage access" from the menu on the left, and then click the green "Invite a collaborator" button.  You'll need to know your collaborator's GitHub username. (Note: 'Manage access' is also where you can make a repository private vs. public, if you'd like.)

If time allows, try adding others from your breakout groups as collaborators. Practice with your teammates the workflow above, where one person creates a branch, edits, commits, pushes changes, and makes a pull request (steps 1-10), another persom reviews and merges the changes (step 11), and the first person cleans up their local repository and make sure it includes the new changes (step 12-13). You can also purposefully create some merge conflicts and practice resolving them.


<div style="page-break-after: always;"></div>
<br>


## VI. Building off of someone else's GitHub repository with forking (and contributing back to it with pull requests!).

Now let's say you want to contribute to someone else's project, but you're not an owner of the repository.  Maybe you're contributing to a large open source project, or you are looking at a friend's project and have an idea for a cool feature you could build using their project as a starting point.

**Homework**: Use the procedure below to fork the repository at https://github.com/karink520/TuftsGitHubSampleToUpdate, correct one typo (leave the rest for classmates!), and make a pull request so I can merge your change.

1. In your web browser, navigate to the repository on GitHub that you wish to use as a starting point.  On the top right of the window, you'll see "Fork" with an icon and a number next to it.  Click on "Fork" to fork the repository, which means making a copy of the repository.  The copy  gets added to your own GitHub account, and you are its owner.  Thus, once you've forked the repository, you can make changes to the copy without changing the original project that you forked.

2. Clone the repository that you've forked.  Forking creates a copy of someone else's GitHub repository on your own GitHub account.  Cloning creates a copy of a remote repository that you own (e.g. the repository that your fork created!) on your local machine. Type something like:

    `git clone https://github.com/your_user_name_here/repository here.git`

If you want to know the right url to use above, you can click the "Clone or download" on GitHub in your new copy of the repository.  Cloning not only copies the repository locally, but connects the local copy to the remote repository and names the remote "origin".

**Note:** If all you wanted to do was copy somebody's project and use it as a starting point for your own, you're now done.  You have a local and remote repository that are copies of the original, and you can work with them as much as you want without changing the original repository that someone else owns on GitHub. If you want to actually *contribute back* to the original project, you'll want to follow the following steps.


3. Connect your local repository back to the *original* repository that you forked.  This means your local repository will be connected to *two different remote repositories* - one connection to your own GitHub account, and another to the repository from which you forked.  To make the connection, use: 

    `git remote add name_for_remote git://github.com/other_user/their_repo_name`,

where you include your own short name for the remote (`upstream` is common, but you can use what you like here), fill in the correct information for `other_user` and `their_repo_name` as well.

4. Edit the files, and use Git to add and commit the changes.

5. Push the committed changes to your own remote repository on your GitHub account (recall that it has the short name `origin`), by typing:

    `git push origin master`

6. On GitHub, go to the repository on your account, and click the "Pull Request" button, you'll see both your repository and the original.  Your pull request is asking the owner of the original to include you your changes into their project.  You will see both their repository and yours.  Write a helpful message about what changes you have made.  If the other developer thnks your changes make sense to include, they can merge the pull request.  If not, they can choose not to, or can write back asking you to make some changes before they merge it.

7. In the future, the upstream project is likely to continue to evolve without you. So, if you want to make more contributions later on start by fetching and merging from the original project repo first, to make sure your version of the project is up to date with the master branch of the upstream project.  We can do this with:

    `git fetch upstream`

    `git merge upstream/master`

    (Here upstream refers to the original repository on someone else's GitHub account.)

With these skills, you can make valuable contributions to others' projects and to open source software!


<div style="page-break-after: always;"></div>
<br>

## VII. Appendix: Additional topics and troubleshooting

### Forget to fetch and merge and/or to create a branch before you started editing?  Git stash to the rescue!  

1. The `stash` lets you temporarily tuck away your changes for safe keeping.  Type:

    `git stash`

2. Do the step(s) that you had forgotten to do before (fetching and merging and/or creating a new branch)

3. Retrieve the changes that you had stashed, and put them on top of the code that is now up-to-date (if you needed to fetched and merged) and/or on the proper branch (if you needed to checkout the propor branch), by typing:

    `git stash pop`

### Undoing changes and reverting to previous commits (and some notes of caution!):

Type `git log` and you'll see a list of commits.  They each have a long string of letters and numbers, which is a hash that identifies them, as well as the commit message you wrote.
Maybe one of those commits is better than what you have now and you'd like to go back to it.  There are a few different ways to do this, depending on what exactly you're trying to do. To understand these options, see: https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things, https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting, and overview this blog post: https://stackabuse.com/git-revert-to-a-previous-commit/.  **CAUTION**: As these resources note, b careful with commands like `git reset` (especially `git reset --hard`) and `git checkout` (especially in the context of `git checkout --file`) - these commands can lead to losing work permanently.

### Seeing what has changed with git diff
You can use <a href="https://git-scm.com/docs/git-diff">git diff</a> to make comparisons, e.g. between two different commits.

### Have files that you don't want to track?  Add them to a gitignore file.

If you have files in your repository's folder that you don't want to track, you *could* just omit them from your
`git add` statements.  But you may want to be a little more careful, so that you don't start tracking them by accident (especially if they contain sensitive content that you do not want to share on GitHub).  You can create a file with the name `.gitignore` and put in it a list of files that you want git to ignore, and those files will remain untracked.  You can also use .gitignore to make sure that Git ignores all files that match a certain pattern, such as all files that end in `.zip`.  See more information here https://help.github.com/en/github/using-git/ignoring-files and an example .gitignore file here https://gist.github.com/octocat/9257657.

### Use ssh to make connecting to GitHub easier and more secure.
You can connect to GitHub and authenticate with SSH, instead of entering your password.  See information: https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh, or a more concise how-to, here: https://jdblischak.github.io/2014-09-18-chicago/novice/git/05-sshkeys.html

### Use GitHub actions for continuous integration (CI), and keep your code high quality:
GitHub actions allow you to automatically run certain steps or checks every time someone on your project makes a pull request.  For example, you might want a test suite to run, or you might want to run a Python linter to check syntaxing or formatting.  You can read more about GitHub actions here: https://github.com/features/actions.


<div style="page-break-after: always;"></div>
<br>

## VIII. Resources

There are MANY resources on the internet for learning Git, whether you want an in -depth tutorial or are trying to answer a specific question. See what you can discover with searching; for specific questions, StackOverflow is a great resource!

Here are a few particular resources that might be useful:

[Dangit, Git!?!](https://dangitgit.com/) is a great resource for getting yourself out of trouble with Git.

[GitHub Guides](https://guides.github.com/introduction/git-handbook/ ) includes resources about Git and GitHub.

This [resource](https://learngitbranching.js.org/) is a browser game for learning about Git branching.

This [tutorial](https://kbroman.org/github_tutorial/) bills itself as “a minimal tutorial”, and is a good concise reference.

[Atlassian's tutorial site](https://www.atlassian.com/git/tutorials) includes detailed guides about Git. Atlassian makes BitBucket, which is another web-based hosting system for version control repositories and an alternative to GitHub.  The the tutorials around Git itself are applicable to both GitHub and BitBucket. They also have
 a helpful [Git cheat-sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)

A [lecture](https://missing.csail.mit.edu/2020/version-control/) from MIT CSAIL's "Missing Semester", a lecture and bottom-up explanation of Git that is very helpful if you want to understand how Git works underneath the interface.