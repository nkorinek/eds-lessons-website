---
layout: single
title: 'Sync a GitHub Repo: How To Ensure Your GitHub Fork Is Up To Date'
excerpt: "When you are working on a forked GitHub repository you will need to update your files frequently. Learn how to update your GitHub fork using a reverse pull request."
authors: ['Jenny Palomino', 'Leah Wasser', 'Max Joseph']
category: [courses]
class-lesson: ['git-github-collaboration-tb']
permalink: /courses/intro-to-earth-data-science/git-github/collaboration/update-github-repositories-with-changes-by-others/
nav-title: "Sync GitHub Repos"
dateCreated: 2019-09-06
modified: 2019-10-08
module-type: 'class'
course: "intro-to-earth-data-science-textbook"
week: 3
sidebar:
  nav:
author_profile: false
comments: true
order: 3
topics:
  reproducible-science-and-programming: ['git']
---
{% include toc title="On This Page" icon="file-text" %}

<div class='notice--success' markdown="1">

## <i class="fa fa-graduation-cap" aria-hidden="true"></i> Learning Objectives

After completing this page, you will be able to:

* Sync your fork of a GitHub repo using **GitHub.com**.
* Update your local clone of your forked repo using `git pull`.

</div>

** how to update on GitHub

github-commits-behind-master-abc.png

TODO: create animated gif that shows the repo being out of sync and behind and then syncing...

## Syncing GitHub Repos

When you are collaborating with others on a project, there are often changes
being made to the repo that you (and others) are contributing to. It is important keep your fork
up to date or in sync with those changes as you work. Keeping your fork in sync
with the central repo, will reduce the risk of merge conflicts (a topic that you will learn more about in a later chapter).

A merge conflict occurs when two people edit the same line in a file. Git does not know how to resolve the conflict (which changes to keep and which to remove). When git doesn't know how to resolve a conflict, it will ask you to manually fix the conflict.

Pretend that you are working on a fork of your colleagues repo. Your colleagues repo is the final home for the code and content that you are working together on collaboratively. You colleague and others in your group, may be updating code while you are working. It's important to ensure that your fork is in sync with your colleagues repo, ideally before making a new pull request to that repo.

Your repo being in sync refers to your fork having all of the commits or changes
to the code and files that have been made to the parent repo.

# TODO: Image showing a fork that is behind the parent ... and maybe one that's ahead???


There are a few ways to update or sync your repo with the central repo (your colleagues repo).

1. You can perform a "Reverse Pull Request" on GitHub. A reverse pull request will follow the same steps as a regular pull request. However, in this case, your fork becomes the **base** and your colleague's repo is the **head**. If you update your fork this way, you will then have to PULL your changes down to your local clone of the repo (on your computer) where you are working.  
2. You can manually set or pull down changes from the central repo to your clone locally. This can be done using bash. When you update your local clone, you will then need to push the changes or commits back up to your fork on github.com

This lesson will focus on syncing your fork using a reverse pull request approach on GitHub.com

TODO: Image showing fork, clone and central repo (i imagine a triangle type graphic showing 1 and two... the order being different.. ) Ally could work on this.

## Sync Your Forked GitHub Repo Using A Pull Request

To sync your forked repo with the parent or central repo you:

1. Create a pull request on **GitHub.com** to update your fork of the repository from the original repository, and
2. Run the `git pull` command in the Terminal to update your local clone. The following sections review how to complete these steps.

<figure>
 <a href="{{ site.url }}/images/earth-analytics/git-version-control/github-sync-repo.gif">
 <img src="{{ site.url }}/images/earth-analytics/git-version-control/github-sync-repo.gif" alt="An animated gif showing you how to sync a GitHub repo on GitHub.com. Note that you can also sync individual branches within a repo using this same approach."></a>
 <figcaption>An animated gif showing you how to sync a GitHub repo on GitHub.com. Note that you can also sync individual branches within a repo using this same approach.
 </figcaption>
</figure>

### Update Your Forked Repo on Github.com

To update your fork on **GitHub.com**, navigate in your web browser to the main **GitHub.com** page of your forked repository: `https://github.com/your-username/example-repository`.

On this web page, create a pull request by following these steps:
1. Click on the `New pull request` button to begin the pull request
2. On the new page, choose your fork as the **base fork** and the original repository (e.g. your colleague's repo) as the **head fork**.
   When you create this pull request, you will see what files will be updated in your fork. **IMPORTANT: You need to click on the text `compare across forks` to be able to update both the base and head forks appropriately.**
4. Then, click on `Create pull request`.
5. On the new page, click on `Create pull request` once more to finish creating the pull request.

<figure>
 <a href="{{ site.url }}/images/earth-analytics/git-version-control/github-create-reverse-pull-request.gif">
 <img src="{{ site.url }}/images/earth-analytics/git-version-control/github-create-reverse-pull-request.gif" alt="You can update your fork with changes made to the original Github repository by creating a pull request from the original repository to your fork."></a>
 <figcaption> You can update your fork with changes made to the original Github repository by creating a pull request from the original repository to your fork.
 </figcaption>
</figure>

After creating the pull request, you need to **merge the pull request**, so that the changes in your colleague's repo are merged into your fork.

To merge a pull request:

1. Open up the pull request if it's not already open on Github
2. Click on the green button at the bottom of the pull request page that says `Merge pull request`
3. Click on the `Confirm merge` button.  

Once you have conformed the merge, all of the changes from your colleague's
repo are in your repo. Return to your fork on GitHub.com. You will see the
changes that you have just merged into your fork.

<figure>
 <a href="{{ site.url }}/images/earth-analytics/git/github-merge-reverse-pull-request.gif">
 <img src="{{ site.url }}/images/earth-analytics/git/github-merge-reverse-pull-request.gif" alt="After creating a pull request, you merge the pull request to apply the changes from the original repository to your fork."></a>
 <figcaption> After creating a pull request, you merge the pull request to apply the changes from the original repository to your fork.
 </figcaption>
</figure>

If you update your fork on GitHub.com, you then need to update your files locally. The steps to do that are below.

### Update Your Local Clone

Once you have synced your fork on github.com, you are ready to update your cloned repo on your local computer. To pull down or copy the changes merged into your synced fork, you can use the Terminal and the `git pull` command.

To begin

1. On your local computer, navigate to your forked repo directory.
2. One you in the forked repo directory, run `git pull`

The code that you type into the terminal might look something like the example
below:

```bash
$ cd path/to/your/repo/here/repo-name
$ git pull
```

Congratulations! You have now updated your local clone with the updates made to the original **GitHub** repository.


For Jenny:
* Need to save copies of all external images using file-names-like-this.png to images/earth-analytics/git-version-control
* Move all images that need it to images/earth-analytics/git-version-control