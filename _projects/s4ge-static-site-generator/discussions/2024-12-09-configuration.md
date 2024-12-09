---
title: Configuration
category: discussion
project: s4ge
date: 2024-12-09
open: true
---


## Conclusion

---

**2024-12-09**

I think that the configuration in Jekyll is not great, especially the collections and the defaults. I think I have a better solution.

First and foremost, anything that can be defined in the front-matter can also be defined in the configuration files.

**Each folder is configurable with a `_config.yml`.** Using a specificity override - like in html/css, where **the most specific is used**.

**Front-matter would be the most specific**, and override any others. Then the folder confgiuration, then the parent folder configuration, and so on. At the project root are project configuration.

**Configuration options will be added as needed.**
