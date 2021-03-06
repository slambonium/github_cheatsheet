#Git  Cheat Sheet

####How to use this cheat sheet.
 Commands look `like this`, and commands that require specific input, such as unique urls, are inside of square brackets, like this: `git remote -v [YourGitHubRepoURL]`.

####What is Git?
  Git is a command line tool used to track files, and allows for version control.

####Git is not GitHub! Git is open source software, GitHub is one of multiple cloud apps you could use to host git repos.  Head to the [GitHub cheat sheet](https://github.com/aric87/github_cheatsheet/blob/master/git-cheat-sheet.md) for GitHub specific topics.

####What is a repository (repo)?
  A repo is a project folder.

####How do I create a repo?
  To create a local repo, simply get your command line to the desired folder, and type  `git init`, This will add the files that track your changes (that is, "initalize" a repository). Next, you will need to tell Git what to track. This can be done by typing `git add -A`. Once you're comfortable with git, learn how to track specific files.
Now that Git knows what to track, tell it to save your all of your changes and why, `git commit -am “type a message”`. This command saves all the changes with a message, which should describe the updates.

####How do I link my local repo to GitHub?
  First, create an empty repo on GitHub.  When you do, GitHub will give you some options. If you have already created a local repo, then follow the last set of options.
  
  Next, connect the local repository you created with your remote repository on GitHub:

`git remote add origin [GitHubRepoUrl]`

 Finally, push your code from your local repository to your remote repository on GitHub:

`git push -u origin master`

With these commands you create a link between your local repository and the GitHub repository and then tell Git to send the local changes to the master branch at GitHub.

####What are branches?
  Branches allow you to section your code. This is used frequently to keep a working code base on one branch, usually the master, and add features or fix bugs on other branches so that the working code isn’t effected. Create a new branch with `git checkout -b [YourFancyBranchName]` When you checkout to a new branch, and only a new branch, your code is at the same point as the branch you came from. You can `git push origin [YourFancyBranchName]` to send the new branch to GitHub.

####Why did my code change when I switched branches?
  Git keeps track of your commits on each branch separately. When you switch between branches, it changes the files to reflect the branch you are on. For example, if I have a gh-pages branch and a master branch already created, and I am working on the master branch, I would push the changes to GitHub. Then, I want to checkout to gh-pages so I could push my changes to that branch, and see them on GitHub. My computer would show me the last version of the gh-pages branch I had on my computer. So how do I get the master branch into the gh-pages branch?

####How do I merge branches, or pull in changes?
  When you have multiple branches, like a gh-pages branch and a master, and  you want to make them the same, there are two options. One is to merge them, and the other is to pull in changes. For both options, you will want to be on the branch that is behind. Each command works slightly differently, so for simplicity sake, I am going to recommend `git pull origin [branch]`.  For [branch] here you want to put the name of the branch that is ahead. For an example, if you work on the master branch and make updates, then push them to GitHub, you want to `git checkout gh-pages` which will change the files to reflect the gh-pages branch. To bring gh-pages up to date with the master branch, type `git pull origin master` Then you can commit the changes, or make more then commit, and `git push origin gh-pages`.

####What happens if I pull changes, and my terminal goes crazy and asks why I am merging?
  This is called Vim. It's a command line text editor. It has its uses, but for beginning users of Git, you can type `:wq` and then enter. It should return you to your regularly scheduled terminal.  If that doesn't work, try hitting escape and then doing `:wq` and enter.  You can learn more about [Vim here](https://twitter.com/iamdevloper/status/473152427970297857).

####So what should my workflow be?
  That is a personal preference. I recommend getting used to pushing, and pulling, and working, before you decide on a specific workflow. However, here is a simple rundown.

1. Create a local repo inside a folder - `git init`
2. Do work on stuff                    - be sure to save your HTML, CSS, etc. files
3. Add files to Git                    - `git add -A`
4. Commit files to Git                 - `git commit -am “first commit!”`
5. Create an empty GitHub repo         - go to GitHub and click "new repository"
6. Link your local and GitHub repos    - `git remote add origin [YourRepoURL]`
7. Push your local repo to GitHub      - `git push -u origin master`


####When do I need to run `git add`?
  Anytime you put new files into your project folder that you want included in your git project, and any time you work on and save your work on existing files.

####When do I run `git commit`?
  When you are ready to save the changes to your Git project. This creates a commit log that you can go back to in the future if you need to revert changes.

####When do I need to run `git pull`?
  When you want to make your current branch reflect another branch.

####What happens if the repo I forked changes? How do I get those changes?
  You can set an upstream remote, by typing `git remote add upstream [https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git]` This will set the original repo as an upstream source. Then you can `git pull upstream [branch]` to get the changes from the branch you want, on the upstream repo. This concept is a little advanced, but you will use it eventually.

###Looking for more? 
Go checkout the [git-tower](http://www.git-tower.com/blog/git-cheat-sheet/) cheat sheet for a more in depth look at Git.
You can also watch @snarechops [video](http://snarechops.github.io/git/help/2015/02/11/github-basics.html)
