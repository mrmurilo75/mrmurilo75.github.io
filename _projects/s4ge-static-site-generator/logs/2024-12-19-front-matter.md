---
title: Single File Front Matter and Config
project: s4ge
category: log
date: 2024-12-19
---

## Status: Done

- Change config to use keyword 'cascade' and config values in reserved keyword '_values'
- Configurations can be accessed in templates by using the file path relative to the source directory (joined with '.'s and without suffix), then '_values' and finally the property to be accessed. For example: `path.to.file._values.title`. This can also be used to access folder structure -related logic, as the only additional information is under the '_values' keyword.

---

## Notes

Given that the current strategy is files middle steps, the yaml should be all in one file. This makes it so that the file structure and its added config and front matter are accessible in the templates thru variables.

One advantage of having variables rather then filters is that it is (mostly) template engine agnostic.

The current implementation creates one front matter file for each in the 'pop_front_matter' task. What will now be done is to load all front matter in a replicated path in yaml. Config is also placed there. This will be accesible in the templates under 'page**s**' variable and the current pages will still be accessible under the 'page' variable.

- [X] Write all front matter in a single YAML file
- [X] Write all config to the YAML file (related to file values)
- [X] Write all config to the YAML file
