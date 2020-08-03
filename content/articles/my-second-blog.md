---
title: My Second Blog Post
description: Learning how to use @nuxt/content to create a blog
img: https://images.unsplash.com/reserve/LJIZlzHgQ7WPSh5KVTCB_Typewriter.jpg?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60
alt: my second blog post
author:
  name: Peter
  bio: All about Peter and what he does and where he works
  img: https://images.unsplash.com/photo-1533636721434-0e2d61030955?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2550&q=80
---

# Custom Injected variables

## Tutorial Nuxt Content with TypeScript

**JS default tutorial: https://nuxtjs.org/blog/creating-blog-with-nuxt-content/**

## Create md file in content/articles

- my-first-blog.md

```
# My first blog post

Welcome to my first blog post using nuxt content module.
dsa

```

## Create new page

```
- mkdir blog folder
- add new dynamic page `_slug.vue`

1. import `vue-property-decorator` (have to install `vue-class-component`)
2. export default class <ClassName> extends Vue
3. fetch data content in @Component with using `asyncData` (async), and set params is `ctx` (it's mean context).

** Context in nuxtjs: `https://nuxtjs.org/api/context`
** ctx will include: $content (javascript default), params

```


