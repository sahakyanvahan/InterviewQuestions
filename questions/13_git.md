<h1 align="center"> Git</h1>

<br/><br/>

## 1. What is Git and why is it useful for software development?
### Answer
> Git is a distributed version control system that allows developers to track changes to their code over time, collaborate with other developers on the same codebase, and maintain a history of all changes made to the code. Git is useful for software development because it enables developers to work on different parts of a project simultaneously, merge changes from multiple sources, and revert to previous versions of the code if necessary.

---
<br/><br/>

## 2. What is the difference between merge and rebase?
### Answer
> In Git, both merge and rebase are used to combine changes from one branch into another. However, they work in slightly different ways.

> When you merge a branch in Git, you take the changes from one branch and apply them to another branch, creating a new commit that represents the combination of the two branches. This creates a new "merge commit" in the branch that you are merging into, which has two parent commits: one for the original branch and one for the branch you are merging in.

> On the other hand, when you rebase a branch in Git, you move the entire branch to a new base commit, effectively replaying the changes from the original branch onto the new base commit. This results in a linear history, with a single branch that incorporates all of the changes from both the original branch and the new base commit.

> The main advantage of merging is that it preserves the original history of both branches, which can be helpful for understanding the context and evolution of the codebase over time. Merge also allows you to easily revert changes if necessary, by simply reverting the merge commit.

> The main advantage of rebasing is that it creates a cleaner and more linear history, which can be easier to understand and follow. This can be especially useful when working on larger projects with many contributors, as it can help to reduce complexity and make it easier to track changes.

> In general, merge is a good choice when you want to preserve the history of the branches and the changes they represent, while rebase is a good choice when you want to create a cleaner and more linear history, or when you need to incorporate changes from a branch that has diverged significantly from the main codebase.

---
<br/><br/>

## 3. What is git stash? Why it is usefull?
### Answer
> Git stash is a feature in Git that allows you to temporarily store changes that you have made to your code, without committing them to the repository. This can be useful in a variety of situations, such as when you are working on a feature branch and need to switch to another branch to fix a bug or work on a different feature.

> When you use git stash, Git will save your changes to a "stash" object, which is stored in the repository. This object contains the changes you have made to the files in your working directory, as well as any changes you have staged but not yet committed. Once the changes are stashed, you can switch to a different branch or perform other actions without worrying about losing your work.

> To use git stash, you simply run the "git stash" command, optionally providing a message to describe the changes you are stashing. You can then switch to another branch, make other changes, or perform other actions as needed. When you are ready to retrieve your stashed changes, you can use the "git stash apply" command to apply the most recent stash to your working directory, or "git stash pop" to apply the most recent stash and remove it from the stash list.

> Git stash can be particularly useful in situations where you need to switch between tasks quickly, or when you need to work on multiple tasks simultaneously. It allows you to save your work without committing it to the repository, which can help to keep your commit history clean and organized. It is also useful when you need to share changes with other developers for review or testing, as you can easily create a stash and send it to others for review.

---
<br/><br/>

## 4. What branching strategies do you know?
### Answer
> In Git, branching is a powerful tool that allows you to create multiple versions of your codebase and work on them independently. However, managing multiple branches can be complex, especially when you are working on a larger project with many contributors. To make the process of branching and merging easier, many teams use a branching strategy.

> A branching strategy is a set of guidelines and best practices for how to use branching in Git. It defines how and when to create branches, how to name them, how to merge changes between them, and how to manage conflicts and other issues that can arise when working with multiple branches.

> There are many different branching strategies that you can use in Git, depending on the needs of your team and the complexity of your project. Some of the most common strategies include:

> * **Gitflow:** A popular branching strategy that involves creating a "master" branch for production-ready code, a "develop" branch for ongoing development, and feature branches for new features or changes.

> * **Trunk-based development:** A strategy that involves using a single "trunk" branch for all development, with changes merged in as soon as they are ready. This approach is often used for smaller projects with a single team of developers.

> * **Feature branching:** A strategy that involves creating a new branch for each feature or change, and merging those branches back into the main branch once they are complete. This approach can be more complex, but it allows for greater control over the development process and easier tracking of changes.

> * **Release branching:** A strategy that involves creating a new branch for each release or deployment, and using that branch to stabilize the code and prepare it for release. This approach can be useful for larger projects with a longer release cycle.

> Each branching strategy has its own advantages and disadvantages, and the best strategy for your team will depend on a variety of factors, such as the size and complexity of your project, the number of developers on your team, and your overall development process. The key is to choose a strategy that fits the needs of your team and helps you to work more efficiently and effectively with Git.

---
<br/><br/>
