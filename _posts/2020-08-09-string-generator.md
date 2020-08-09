---
title: Cryptographically-secure string generator
layout: post
---

For the [Grinnell Rent Assistance](https://github.com/grinnell-rent-assistance) project, 
we have opted for temporary link system, opposed a full-fledged login in system. This saves us the hassle of implementing
a full login system for a infrequently accessed service, while also minimizing user information stored and other security concerns. 
In order for this to function properly, we needed to implement a secure way to generate temporary links. Using Node's crypto library, 
we can generate bytes, then convert the bytes to a hexadecimal string representation;

Here is the gist.

<script src="https://gist.github.com/ilknarf/b3ff2def3f457137c8ef524ce57f8c56.js"></script>
