---
title: Improve Templates & Source
project: s4ge
category: log
date: 2024-12-18
---

## Status: Done

Added css assets directly to source - will then be copied to site on the same relative path.

The path in config should be placed as absolute, but in fact be relative to the source root, since that will be replicated on output.

The templates and css have been generated with AI.

Something that came up was, for testing we can just access the file in a browser. We could add a debug to config that adds the absolute user's home path for testing or comething like it. TBD

