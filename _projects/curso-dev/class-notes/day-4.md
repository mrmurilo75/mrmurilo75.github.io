---
title: Day 4 - NPM Commands & Next.js Routes
category: class-note
project: curso-dev
---

## TL;DR

To run a depencies command, add an entry to the *"scripts"* map of our *packages.json* file. Run it with `npm run $ENTRY_KEY`.

To run the *Next.js* development server use `next dev` (through as *"script"* entry in *package.json*).

Routes are defined by the files in the *'pages'* folder, the route being the file path and name. The function ran when accessing these routes is the exported default (using `export default FunctionName;`).

---

## Related Commits

* [add 'dev' script for next.js server](https://github.com/mrmurilo75/clone-tabnews/commit/cde9e7665d3b9960d56413b114ad35bb3a71a172)

* [add index page with Home function](https://github.com/mrmurilo75/clone-tabnews/commit/1bc0ab6b79666cd40ace5f7f5ff8472c00889d32)

* [gitignore .next folder](https://github.com/mrmurilo75/clone-tabnews/commit/c5237d10d664735859517f0ad358470b3b1d384a)

---

## NPM - Dependencies commands

To run a depencies command, we need to access it through the *"scripts"* map of our *packages.json* file. 

To run a local *Next.js* development server we need to run the command `next dev`, so we'll add the `dev` *"script"* to our **packages.json** by adding the following:

```json
"scripts": {
    "dev": "next dev"
}
```

To run it, we'll use the `npm run` command and the script name: 

```bash
$ npm run dev
```

## Next.js Routing

*Next.js* has 2 routing techniques, but in this course we'll use the pages directory.

### Pages

Every file inside the *pages* directory becomes a public route with the directory path and the file name (with the exception of the file "index.js", which only uses the directory path).

These routing files define functions that return HTML, such as:

```javascript
function Home() {
    return <h1>Test</h1>
}
```

But so our server know which function to run, we'll export a given function as the default, with:

```javascript
export default Home;
```
