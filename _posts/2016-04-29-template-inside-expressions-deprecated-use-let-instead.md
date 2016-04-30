---
layout: post
title: 'angular 2 - Template parse warnings: "#" inside of expressions is deprecated. Use "let" instead! (ngFor)'
category: angular2
tags: [angular2, angular]
lang: 'en'
comments: true
share: true
mathjax: false
imagefeature: picture-38.jpg
published: true
---

So you get on your console some warnings:

<!--more-->

```
Template parse warnings:
"#" inside of expressions is deprecated. Use "let" instead! ("
        <ul>
          <li [ERROR ->]*ngFor="#i of items" >
            {{ i }}
          </li>
"): List@2:14
```

# Fix

Replace the `#` with `let`.

Instead of:

```
<li *ngFor="#i of items">
```

Use:

```
<li *ngFor="let i of items">
```



