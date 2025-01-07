---
title: Day 9 & 10 - Github Issues
category: class-note
project: curso-dev
date: 2024-11-12
---
[class-notes-day-8-and-9]: {% link _projects/curso-dev/class-notes/day-8-and-9.md %}
[milestone-0]: https://github.com/mrmurilo75/clone-tabnews/milestone/1
[custom-domain-issue]: https://github.com/mrmurilo75/clone-tabnews/issues/1
[editor-config-issue]: https://github.com/mrmurilo75/clone-tabnews/issues/2
[build-in-progress-page-issue]: https://github.com/mrmurilo75/clone-tabnews/issues/3


Github issues are a powerful tool for project planning and tracking, especially for open-source software projects. 

On the project homepage there is a tab *"Issues"* where they live. An issue can be assigned to people, be part of a Kaban board, and much more. We'll dive deeper into their features in the future.

## Milestones

In the issues tab, we can create *"Milestones"*. There will be the major sections, features, or achievements in the development of your project.

It is important to note that at the planning stage we don't yet know the form that the project might take, neither the challenges and issues that may arise.

As development progresses and we acquire more knowledge, the Milestones (and other plans) will likely change. So instead of trying to foresee the future and create an exact plan, we should use our estimate to decide what our current *Milestone* should be. Then only create the one - or few - that we'll be using now.

### Associate Issues

When we create an issue, we can associate it to a Milestone. Github will then update the Milestones progress to show open and closed issues, and calculate a progress percentage based on it.

#### Tasks of an Issue

In the text of an issue we can add the following to create a checklist item:

```text
- [ ] Some task
```

This used by Github to automatically calculate our progression both in the issue and the milestone, if associated.

---

## Related Issues

* [Milestone 0: Build In Progress][milestone-0]
    * [Configure a custom domain][custom-domain-issue]
    * [Code styling and editor configuration][editor-config-issue]
    * [Create a "Build In Progress" page][build-in-progress-page-issue]
