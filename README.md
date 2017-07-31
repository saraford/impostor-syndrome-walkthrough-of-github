# Impostor Syndrome Walkthrough of GitHub
Talk from [Kansas City Developer Conference 2017](http://www.kcdc.info/sessions)

#### Abstract
As a long time Windows user and .NET developer, I’ve challenged myself to level-up my skills using Git and GitHub. As an industry, I feel we provide great content for beginners and for experts, but how do we target content for people in the intermediate category? To answer this question, I'm going to blog every. single. day. in 2017 about something new I’ve learned about using Git and GitHub. I’m hoping that showing my day by day progression can help others who are in similar situations, i.e. trying to reskill after years of industry experience.

I've been calling this guide "a penultimate guide" because I don't know what I don't know yet. I don't know which tips will be the best ones for an ultimate guide to Git(Hub). However, by the time KCDC rolls around, I will be more than half way through the Git(Hub) Tip of the Day series. This means I'll be half-way to an ultimate guide for intermediates leveling-up their skills to more advanced topics. This talk will cover the best of the best tips for this half-way point.

## Intro

So, um, about that blog every. single. day. idea... 

I made it until May 8th or **35% of my goal.** I left GitHub (the company) that week for a true summer vacation. Having said that, I still found the challenge rewarding. Forcing myself to blog about what I did **not** know forced me to learn or ask for help.  

If I could go back in time, this is the readme file I'd give myself. It contains the major lightbulb moments where Git(Hub) concepts click. Hopefully you'll (or somebody you know) will find it useful.

P.S. This is a git pun-free zone.

P.P.S. If you are just getting started, jump to the new machine setup section. 

## Part 1 - Visualizing Git Commands

1. **GitHub offers an [excellent cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf).** Print it out! 
2. **Setup your practice area using bash commands**
    - GitHub Services offers On Demand Training - shows [how to use a bash script](https://services.github.com/on-demand/git-trouble/git-set-up) to quickly create a test repo
    - Make sure to `git init` first!
    - See [Tip 086 for walkthrough](https://saraford.net/2017/03/27/how-to-write-a-bash-or-powershell-script-to-quickly-create-test-repos-086/)
3. **ohshitgit.com I've committed on master**
    - http://ohshitgit.com/#accidental-commit-master
4. **Git Visualization Tool**
    - A couple of GitHubbers created a [Git Visualization Tool](https://saraford.net/2017/03/22/how-to-demystify-git-commands-using-visualizing-git/)
    - This was my NEO WHOA moment - git branches are just pointers. 
    - Now to visualize what `git reset HEAD~ --hard` actually did 
    - See [Tip 082 for walkthrough](https://saraford.net/2017/03/23/how-to-fix-the-oh-no-ive-accidentally-committed-on-master-instead-of-a-branch-082/) 
5. **git reflog (cmd line vs visualization tool)**
    - Go back and demo in cmd line - OH NO MY FILES ARE GONE I HATE GIT IT IS THE WORST WHY DIDN'T I SAY IN AREOSPACE ENGINEERING WHY DID I MAKE SO MANY BAD CHOICES IN LIFE
    - Remember your training - go back to the visualization tool. notice the commits are still there, but with a dashed line.
    - See [Tip 87 for walkthrough](https://saraford.net/2017/03/28/how-to-recover-from-the-oh-no-i-did-a-git-reset-and-now-my-files-are-gone-087/)
    - Demo reset in visualization tool, then git log. Notice we're all back to where we were before - remember these git branches are just pointers.
6. **Revert vs reset (demo in visualization tool)**
    - Revert - this doesn't change history. It creates a new commit. 
    - Reset - let's just pretend everything after this point never happened
    - And git reflog still shows the truth for both commands
    - See [Tip 084 for Revert walkthrough in command line / visualization tool](https://saraford.net/2017/03/25/how-to-use-git-revert-to-undo-a-previous-commit-084/) 
    - See [Tip 085 for Revert in Visual Studio](https://saraford.net/2017/03/26/how-to-revert-changes-in-visual-studio-085/) 
    - See [Tip 087 for Reset walkthrough](https://saraford.net/2017/03/28/how-to-recover-from-the-oh-no-i-did-a-git-reset-and-now-my-files-are-gone-087/)
7. **Merging branches in visualization tool**
    - I always speak in full sentences. "I want to merge <branch> into <my current branch>"  
    - visualization tool can't do a --no-ff (no fast forwards)
    - See [Tip 88 for walkthrough](https://saraford.net/2017/03/29/how-to-create-a-branch-in-visual-studio-088/)
8. **You can do an Undo in the visualization tool**
    - if you're following along at home, type `undo` in tool. you'll go back to the point before the branch merge
9. **Rebase**
    - "I want to rebase <branch> onto <my current branch>"    
    - Note how rebase is a destructive action - the commit ids are different 
    - Not done yet! After rebase, have to move master up (same as merging branches)
      - Git checkout master; git merge feature
    - See [Tip 111 for cmd line walkthrough](https://saraford.net/2017/04/21/how-to-visualize-a-rebase-in-the-git-visualization-tool-111/) 
    - See [Tip 114 for Visual Studio walkthrough](https://saraford.net/2017/04/24/how-to-do-a-rebase-in-visual-studio-114/)
10. **Cherry-pick in visualization tool**
    - Switch to cherry-pick
    - git cherry-pick bugfix1
11. **Detatched Head** 
    - Do a `git checkout <some commit id>` and freak out that you're in a detatched head state
    - Do a `git checkout master` to calm back down and stay in your current profession
    - One thing about git that drives me crazy is when you checkout the commit id that master is pointing to, but yet are still in a detatched head state. After seeing this demo'ed in the visualization tool, I felt for hte first time I had a fighting chance using git. 
12. **Limitations of the tool**
    - No working directory, so no way to do interactive rebase
    - no reset `--hard` or `--soft`
13. **More GitHub Tutorials**
    - [GitHub Services On Demand Git Out Of Trouble](https://services.github.com/on-demand/git-trouble/)
    - Note: This tutorial offers "I've pushed" and "I've didn't push" guidance which is awesome!
    
 
