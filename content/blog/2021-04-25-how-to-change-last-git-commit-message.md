---
id: 654
title: 'How to - Change last git commit message.'
date: 2021-04-25T14:09:42+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.com/?p=654'
slug: how-to-change-last-git-commit-message
timeline_notification:
    - '1619339985'
image: /wp-content/uploads/2021/04/image.png
categories:
    - Programming
tags:
    - commit
    - git
    - version-control
---

In today’s post, I will walk you through the steps needed to change the last commit message in git version control.

If you don’t know, git is a very popular, distributed version control system often used in software development to intelligently manages code changes which are done by several people in a large software project.

Most often I face the problem where I need to change my commit message after I make a commit with a bunch of changes. If you are using the git command-line interface, just like I do, then the following are the steps that are needed to change the commit message.

**Steps –**

1. First, check the history with `git log –oneline` to check your previous commit message.

[![](https://mccshreyas.files.wordpress.com/2021/04/image.png?w=866&resize=690%2C218)](https://mccshreyas.files.wordpress.com/2021/04/image.png)<figcaption>git local history  
  
</figcaption></figure></div>As you can see above “Added `GetEmailService()` function” is the last commit message. I want to change it to a more specific message.

2\. To change that run following the git command. Following is the format of that command

`git commit --amend -m "your new message" `  
  
In my case following is my new message.

 [![](https://mccshreyas.files.wordpress.com/2021/04/image-1.png?w=963&resize=700%2C55)](https://mccshreyas.files.wordpress.com/2021/04/image-1.png)<figcaption>Change last git commit message</figcaption></figure></div>3\. Once done, check your history with `git log –-oneline`, your last message commit message will be updated with the new one.

 [![](https://mccshreyas.files.wordpress.com/2021/04/image-2.png?w=1011&resize=700%2C117)](https://mccshreyas.files.wordpress.com/2021/04/image-2.png)<figcaption>Updated message </figcaption></figure></div>As you can see it’s quite easy to change the last commit message in one git command.  
For me these changes were not pushed to the remote repository, but if you have already pushed commits to the remote repository and wanted to update the commit message on the remote repository then along with the above-mentioned steps at the end execute the following command to push new commit message to the remote repository.  
  
`git push --force branch-name`

Make sure to change the branch name with your branch name, to push to that branch. Once done the commit message will be updated in the remote branch as well.

So, this was a short and simple post to the most occurring problem while working with the git version control system. I hope you liked it, if you have any questions or any doubts, please let me in the comment section below.

Thanks for reading…