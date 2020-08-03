# Tutorial Nuxt Content with TypeScript

**JS default tutorial: https://nuxtjs.org/blog/creating-blog-with-nuxt-content/**

## Create md file in content/articles

- my-first-blog.md

```
# My first blog post

Welcome to my first blog post using nuxt content module.
dsa

```

## Create new page

- mkdir blog folder
- add new dynamic page `_slug.vue`

1. import `vue-property-decorator` (have to install `vue-class-component`)
2. export default class <ClassName> extends Vue
3. fetch data content in @Component with using `asyncData` (async), and set params is `ctx` (it's mean context).

** Context in nuxtjs: `https://nuxtjs.org/api/context`
** ctx will include: $content (javascript default), params
