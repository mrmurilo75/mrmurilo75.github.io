---
title: Day 10 - Code Styling
category: class-note
project: curso-dev
date: 2024-11-21
---
[EditorConfig]: https://editorconfig.org/
[Prettier]: https://prettier.io/
[day-4-notes]: _projects/curso-dev/class-notes/day-4.md
[add-editorconfig-commit]: https://github.com/mrmurilo75/clone-tabnews/commit/4dc9cdfe42ea97d114d6259a8f0c91953b01b4ff
[add-prettier-commit]: https://github.com/mrmurilo75/clone-tabnews/commit/9a95b477fe02fb432a7f1d404656187c536d3dcf
[apply-prettier-commit]: https://github.com/mrmurilo75/clone-tabnews/commit/9ad61e229d2694e11d526593883c436cb9395097
[code-styling-issue]: https://github.com/mrmurilo75/clone-tabnews/issues/2


## Standard Code Styling

Everyone will have a preference on how they write their code, like the very famous 'tabs vs. spaces' discussions. But without a standard the code base will get messing and it will be like going to a city you never been to without a map. Coding standards and best practices make it easier to know where things are and give you a familiar-looking code that is faster and easier to read and write.

### EditorConfig

To keep code formatted **while writing it** we'll use the [EditorConfig] standard. We'll create a file `.editorconfig` and define the standards we want to apply. Depending on the editor being used, it might require a plugin.

### Prettier

To garantee that the code is **kept formatted** we'll use a code formatter called [Prettier]. It can be run on our local development machine to reformat written code, used as a checker before we push code, and also in the Continuous Integration (CI) to test that the code pushed follows the standards.

#### Installation

[Prettier] will be installed as a dependency for our project through `npm`, but only for the development environments. To do this we add the option `--save-dev` to the install command, or the short form `-D`, like:

```bash
$ npm install prettier --save-dev
```

#### Usage

As we learn in [Day 4][day-4-notes], to run a dependency command we'll need to add a *"script"* entry. For prettier, the two main usages will be to **check** and to **apply** the formatting. So to do those we'll add the respective entries:

```json
...
  "scripts": {
    ...,
    "lint:check": "prettier --check .",
    "lint:fix": "prettier --write ."
  },
...
```

Lastly, we can configure our editor to *apply* the format automatically everytime we save the file.

---

## Related Commits

* [add `.editorconfig`][add-editorconfig-commit]
* [add `prettier`][add-prettier-commit]
* [apply `prettier`][apply-prettier-commit]

## Related Issues

* [Code styling and editor configuration][code-styling-issue]
