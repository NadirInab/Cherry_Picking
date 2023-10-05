# Cherry_Picking 🍒👩‍💻 

<p> 
This repo provide an overall view about ```git cherry-pick``` command. 
    is one of the most useful commands in Git and also it does not change your         current Git history rather it adds commits to it. In this tutorial, we will be     explaining more about Git Cherry Pick commit and how you can use the Git cherry     pick command for including specific changes to your current branch. </p>
    
#### We'll get to know the following 👉 : 
    
- What are the use cases ?
- How to use it ?

<div>

### Use Cases of cherry pick : 
Although ```git cherry-pick``` is useful, it isn't as recommended as traditional merges in many scenarios where cherry-picking would be useful.
However, ```git cherry-pick``` is comes pretty handy in some scenarios such as : 

##
- Team collaboration 🦾.
     
When a team of developers collaborate in the same codebase it makes it possible for other to review and give feedbasks  which help identify and fix bugs also ensure that everyone is on the same page, eventually improve the communication & quality of your code, besides that it increase the productivity and save both time 🕓 and ressources 🏃️.

In this case git cherry-pick command helps applying individual commits from one branch to another, this can be useful to : 

- Backporting bug fixes: If you have a bug fix that needs to be applied to multiple branches, you can use cherry-pick to apply it to each branch individually.
- Sharing features: If you are working on a feature that you want to share with other developers, you can cherry-pick the commits for that feature to their branches.
For example : A developer is working on a new feature in a development branch. Once the feature is complete and tested, the developer cherry-picks the commits for the feature to the main branch. This allows other developers to start using the new feature immediately.
##
 - Bug hotfixes 🐞 🔧
 
When a bug is discovered it is important to deliver a fix to end users as quickly as possible. For an example scenario,say a developer has started work on a new feature. During that new feature development they identify a pre-existing bug. The developer creates an explicit commit patching this bug. This new patch commit can be cherry-picked directly to the main branch to fix the bug before it effects more users.
     
</div>

#### 

### How to use ```git cherry-pick``` :

In order to demonstrate how to use git cherry-pick let us assume we have a repository with the following branches: 
- Main 
- Feature
##
In this example, we are only interested in the seconde commit of the feature branch, applying a traditional merge will bring the whole code from the feature branch and create a new commit in the tip of the main branch. In this case ```git cherry-pick``` is very handy.

First of all Identify the commit-hash : 

```md
    git log -oneline feature
```

Change the branch you want to apply the changes to : 

```md
    git checkout main
```

Simply run : 
```md
    git cherry-pick "commit-hash-of-seconde commit-in-feature"
```


<div align="center">
<img src="https://www.dolthub.com/blog/static/b52e7ebc154750e60a0316184bc9cce0/75609/cherry-pick.png" alt="Image Alt Text">
</div>

### Now let's check step-by-step a good illustrations of what cherry-pick does — and an animation of these illustrations. src = stack overflow :

### Before cherry-picking

#### So basically we are going to do a cherry-pick of the commit L from the branch feature .

<div align="center">
<img src="https://i.stack.imgur.com/x1R6o.jpg" alt="Image Alt Text">
</div
    
### Now let's cherry pick the commit L : 
```git cherry-pick feature~2```
<div align="center">
<img src="https://i.stack.imgur.com/H1NDD.jpg" alt="Image Alt Text">
</div>

### After performing the command our working flow will be as follow :

<div align="center">
<img src="https://i.stack.imgur.com/LpDH8.jpg" alt="Image Alt Text">
</div>

### Animated :

<div align="center">
<img src="https://i.stack.imgur.com/j2D9C.gif" alt="Image Alt Text">
</div>

#### PS : 

```md
The commit L' is from the user's point of view the exact copy of the commit L.
Technically speaking, it's a new, different commit, because L contains a pointer to K as its parent while L' contains a pointer to E .
```

## Execution options of ```git cherry-pick``` : 
### Depends on the situation Useful options could be used with git cherry-pick : 

- ``` git cherry-pick --no-commit```
#### The --no-commit option will execute the cherry pick but instead of making a new commit it will move the contents of the target commit into the working directory of the current branch.

- ```-edit```
#### Passing the -edit option will cause git to prompt for a commit message before applying the cherry-pick operation.


