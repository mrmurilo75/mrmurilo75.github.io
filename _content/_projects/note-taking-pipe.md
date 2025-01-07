---
layout: page
title: Note taking
category: index
project: note-taking
---

The app interface at the very first is like an Instant Messaging app, where you simply send notes and the AI organizes the information for you.

You'll have public information like movies that will be placed on a public folder and in proper informtaion system, maybe like a db, then rendered to site.

You can also classify information as private, this can be simple daily tasks or personal notes. The advantage is that it also goes into a public folder and notes.

The AI is completely disconnected from the information. It simply links and formats. The ledger of instant messages is kept intact, new articles (the output of the organization by the AI). These are also versioned. A separate validation AI makes sure that the editing AI is not deleting already existing information and if so the user must validate the changes (like a push). - Taking inspiration from the workflow of git and pull requests, where someone else - in this case the AI - makes the changes to the code base, and someone else then validates it and merges. Additional steps such as pre-commit and post- and pre- push hooks also makes sense here.

This whole things makes a lot of sense when using git/github as the back bone, with authentication and pushing changes to a branch.

