# Github tutorial-workshop
Workshop scratch area for demo purposes

* author: [Emmanuel Joliet](https://caltech-ipac.slack.com/team/ejoliet) ejoliet@ipac.caltech.edu

## Demo

The demo will cover:

* github tool: graphs/metrics, pull request, code review
* commits and pushes
* [branches and merging](https://www.atlassian.com/git/tutorials/using-branches)

Participants will need a github account to be able to interact with the IPAC repos and [Git](https://git-scm.com/) tool installed locally.

## Hands-on

Participants will be guided through the following steps:

1. **clone** the repos locally on their end (need git software installed)
  * `git clone https://github.com/Caltech-IPAC/grits2018-tutorial.git` 
  * default landing branch should be `dev` (default per repos, this one has rules for PRs!)
    * `git status -sb` to check on which branch you are

2. create your feature/ticket **branch** from `dev` 
  * `git checkout -b [branch name]`, required unique branch name, usually formatted as `ISSUE-ID-meaningful-short-description`
    * for example, let's take a look at epic from JIRA board [IRSA-2060](https://jira.ipac.caltech.edu/browse/IRSA-2060) and pick a ticket, i.e. IRSA-2062 improve the text
    * my branch name will be IRSA-2062-improve-text
    * Will update [scratch.txt](scratch.txt) and make it uppercase
3. Imagine that you get assigned a ticket to update [names.txt](names.txt) with your name 
  * create a branch, append your github `USERNAME` to branch name
  * edit and **change** the file in this repos named [names.txt](names.txt) by adding your name
4. **commit** your changes in your branch: add/commit
    1. `git add names.txt`
    2. `git commit -m"[your message]"`
5. continue changing/adding/commit and check the differences:
    1. `git show`
    2. Check your commit history: `git log` or more fancy `git log --decorate --graph`
    3. *OPTIONAL*: if no commit to be made, at that point, you can: pull or rebase
     * after pulling, check branches pulled: `git branch --all`
     * if `dev` got new things, you will need to rebase in order to avoid conflict at the time you pull request

6. Once done of changes, **push** to server (`-u` flag means that you'll start tracking the branch)
  * First time push: `git push -u origin [branch name]`
  * Your local branch is now synced with remote
  * Next pushes: `git push`

7. **Pull Request**: in github.com, button 'pull request' should appear
  * Show a pull request / code review
  * *OPTIONAL* Show a case of how to [request changes](https://help.github.com/articles/about-pull-request-reviews/)  (and what to do)
    * if request change, need to go to the branch, and
        * change file, git add / commit / (`rebase -i` to squash) / push (steps 3 to 6 above)
        * no rebase there because branch is already in server / no force push either
  * wait for approve (repo rule in settings)
    * did you update the counter in [sum-team.txt](sum-team.txt) and run `./team-test.sh`? Jenkins will complain
8. Show when approve changes and merge from github
  * Branch can be deleted from github after merged

9. OPTIONAL: If merge conflict (typically, same line have changed in the meantime: github will suggest commands and guidelines to solve and merge locally

10. Once merged, typically the branch can be deleted from github from the same pull request page.


### Need Help?

* [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Git documentation](https://git-scm.com/docs)
* [Github guides](https://guides.github.com)
* [git config aliases and more](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config) or use command `git config --global --edit`
* Learn more about [credentials](https://help.github.com/articles/caching-your-github-password-in-git/), clone with username, prompting your password: `git clone https://username@github.com/username/repository.git`
* .gitignore? convenient when `git add -u`
* [Useful git tips & tricks - autocompletion!](https://git-scm.com/book/en/v1/Git-Basics-Tips-and-Tricks)
* [Pull request template](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/)
* [To Fork or to clone, that is the question!](http://stackoverflow.com/questions/9257533/what-is-the-difference-between-origin-and-upstream-on-github/9257901#9257901)
* [Leave message in Slack #workshop](https://tmt-stil.slack.com/messages/C4JV40FRD)
* [Slack me](https://tmt-stil.slack.com/messages/@ejoliet)
