---
title: Day 3 - Node.js & NVM
category: class-note
project: curso-dev
---

## TL;DR

In this course will be using the **Node.js** environment. 

We'll use **nvm** and the **.nvmrc** file to set the Node.js version. The .nvmrc file contains only the version name, such as `lts/hydrogen`, and can be set using `nvm install`.

The depencies will be installed and tracked using **npm**. Initializing with `npm init` will create the **package.json** file.

Depencies can then be added using `npm install target_name@target_version` (for example `next@13.1.6`). They will then be automatically added to the *package.json* file.

A **package-lock.json** file is also created, and contains the **dependencies tree**. To replicate an existing environment use `npm ci`.

---

## Related Commits

* [add .nvmrc](https://github.com/mrmurilo75/clone-tabnews/commit/32d3f3d52b8a44e38a508e8976e02db1eea0f9e2)

* [add package.json and package-lock.json](https://github.com/mrmurilo75/clone-tabnews/commit/7017beb27ad0605056ba3841717726c009e7ef42)

---

## Node.js

### NVM

To install a **Node.js** version and assign it as default using **nvm** (node.js version manager) run the following commands:

```bash
$ NODE_VERSION=lts/hydrogen
$ nvm install $NODE_VERSION
$ nvm alias default $NODE_VERSION
```

> In this case we are using an environment variable but it could just be written directly in the commands.

For persistency and consistency across the development environments, we can use the **.nvmrc** file. It needs only the recommended version, then it can be installed and set using `$ nvm install`.

```bash
$ NODE_VERSION=lts/hydrogen
$ echo $NODE_VERSION > .nvmrc
$ nvm install
```

### NPM

We'll use **npm** (Node.js Package Manager) to keep track of our dependencies. To initialize the tracking run the following command:

```bash
$ npm init
```

You'll then be prompted to choose some options and enter some information about the project, and then the tracking file (**package.json**) will be created.

The only option we wont use the default is the licence. -- We'll dive deeper later on, for now we'll use MIT. 

Next, we'll add the dependencies using `npm install target_name@target_version`:

```bash
$ npm install next@13.1.6
$ npm install react@18.2.0
$ npm install react-dom@18.2.0
```

> This could be a one-liner with `npm install pack_a@version_a pack_b@version_b`

They will then be automatically added to the *package.json* file, which in following installations can be installed with a simple `npm install`.

#### What about package-lock.json?

Running `npm install` will also create a **package-lock.json**. According to [this question on stack-overflow], this file contains information on the *dependencies tree*, so basically everything npm is installing. 

Therefore, it is an extension of the information in the package.json file and **should be committed to git**. Furthermore, its recommended that you use `npm ci` when you don't want to change the *package-lock.json*, such as when setting up local development from an existing repo.