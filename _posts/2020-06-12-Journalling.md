---
layout: post
title: "Setting up note taking, an exercise in procrastination"
date: 2020-06-12
---

## Why journal

I have discovered that taking notes really helps with keeping my focus on the task at hand, especially these days when attention span has been worn down to a fickle nub by the availability of everything all the time. 

It also results in some kind of documentation that can be shared or read over to remind me where i was up to. Indexing the notes is always an issue though, by date? Or with metadata like tags? The only system that I've kept working with is ordering by JIRA (work notes). But outside work, the subject is much more sporadic - so thinking a date based system would work well.

## Choosing vimiki or vscode-journal

I would prefer to use vimwiki everywhere as Vim is super snappy and quick to load. However at work there are issues getting vim plugins to work across the corporate proxy (probably not insurmountable mind you). So I use the VS code extension vscode-journal. It isn't as fully featured as vimwiki but it's been good as I always have VS Code open and i can just quickly type Ctrl-Shift-J and whack a note in, which gets put in a date indexed file.

## How do i sync across devices?

I want my same journal to be used everywhere, except perhaps for work - don't want to accidently push some code or something outside of the work network or I'll be hauled off to city hall.

Option to investigate - use an S3 bucket? Would this work for android? Quick google suggests its not super smooth.

Currently have it as a github repo, which is fine and dandy but not great for phone option. Why do i want an option for my phone? Because I always have my phone on me and things i need to take a note on have an memory expiry date much shorter than the time it takes to get to a laptop.

### RClone

I've installed RClone, which is a CLI tool for syncing with pretty much any cloud environment. I guessed I could sync with a google drive folder (or S3), which would enable me to access easily on the phone (more easily then Git).

So far I have set up a config for using it with google drive, which was pretty in depth but had a good guide for doing the oauth part so seems to have gone smoothly.

Seems to be able to connect

```bash
alun@alun-XPS-13-9360:~/Cloud/GDrive$ rclone about GoogleDrive:/
Total:   102G
Used:    1.402G
Free:    74.021G
Trashed: 20.216k
Other:   26.577G
```

I wonder if i can sync it

```bash
alun@alun-XPS-13-9360:~/Cloud/GDrive$ rclone sync . GoogleDrive:/Notes/
```

Ohh woops that seemed to sync the empty directory over the two (luckily crappy) files i had in that folder!

Lets maybe try again the other way round eh...

```bash
alun@alun-XPS-13-9360:~$ rclone sync ./vimwiki/ GoogleDrive:/Notes/vimwiki/ --create-empty-src-dirs
```
Well yes that worked, it created the folders on my google drive, cool! The only thing is it just sat there running and didn't finish. Maybe while sync is running keeps it updated?

## Summary

To summise, I find nothing quite as satisfying as procrastinating around a task (my house dashboard) by deeply focusing on a completely tangental tool or new process (journalling). Hope you have enjoyed the journey!

