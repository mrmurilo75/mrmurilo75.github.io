---
title: Notebook Note Groups
project: personal-blog
category: log
---

## Status

Ready to execute. See *Conclusion* below for steps.

---

## Idea

* Have either **entry-points** for sub-notebooks or **singular notes** - create categories
* Filter notebook listing by category
* Update structure [discussion] and add it to notebook index

## Inception

Following suite with the *projects* structuring, we'll use the *"index"* to mark notes that are supposed to be shown in the *notebooks* listing page. Inner notebooks can be created by defining the *"notebook"* variable in the front-matter, both in the respective index and notes. Then, same as in projects, the inner notebooks are free to use the *category* to group notes.

## Conclusion

* In the Notebook listing: 
    * Filter notes with *category* **index***
    * List in two section: 
        * **Notes** - If *"notebook"* front-matter null
        *  and **Notebooks** - otherwise
* Update structure [discussion] with this **Inception**
* and add it to the Notebook listing page