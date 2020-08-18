---
published: true
title: Resolving no-undef eslint error in create-react-app
layout: post
---
While working on a projected bootstrapped with [Create React App](https://create-react-app.dev/), I ran into the following error:

```
Failed to compile.
...
  Line 17:14:  'BigInt' is not defined  no-undef
  Line 53:24:  'BigInt' is not defined  no-undef

Search for the keywords to learn more about each error.

```

As it turns out,
Create React App [deliberately disables usage of globals](https://github.com/facebook/create-react-app/blob/master/packages/eslint-config-react-app/index.js#L19-L23)
in its ESLint config. BigInt is classified as such, even though [it has been merged into an ECMA spec](https://github.com/tc39/proposal-bigint).

In order to resolve this issue, you can either directly reference `window.BigInt`, or add the ESLint directive `/* global BigInt:false */` to each page that uses it.
