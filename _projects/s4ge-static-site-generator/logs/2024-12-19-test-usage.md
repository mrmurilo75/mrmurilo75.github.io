---
title: Test Usage on Pink Space
project: s4ge
category: log
date: 2024-12-19
---
[ebde963]: https://github.com/mrmurilo75/s4ge-static-site-generator/tree/ebde963df0e24587c8b5f14d386de42884c286e6
[test-ebde963-_config]: https://github.com/mrmurilo75/mrmurilo75.github.io/blob/s4ge-ebde963/_config.json
[test-ebde963-projects]: https://github.com/mrmurilo75/mrmurilo75.github.io/blob/s4ge-ebde963/source/projects.md

## Status: Done

I have tried using sample content of this site with the current version of s4ge ([commit ebde963][ebde963]).

### What Worked

- Not *having* to add front-matter was nice, and when adding using only what I truly wanted.
- Even though it's *clearly* not ready, the file structure querying was better than the Jekyll filters (in my opnion)
- Links were cleaner

### What Didin't

- File path not always worked
    - currently they are as root but miss the '/' at the beginning, and file suffixes had to be added ('html')
- Adding direct html with configuration in `_config` was not nice
    - For example, the "path" had to be added directly - see [here][test-ebde963-_config]
- Using file structure query was not nice
    - One especially bad experience was when trying to list folder pages, which means using values of their inner 'index.html' files
        - this also means there was no way to use the start http folder path to see the index
        - see [here][test-ebde963-projects]
