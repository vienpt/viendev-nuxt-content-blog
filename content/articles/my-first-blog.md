---
title: My First Blog Post
description: Learning how to use @nuxt/content to create a blog
img: https://images.unsplash.com/reserve/LJIZlzHgQ7WPSh5KVTCB_Typewriter.jpg?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60
alt: my first blog post
author:
  name: Benjamin
  bio: All about Benjamin
  img: https://images.unsplash.com/photo-1595804850773-4a3fe3444a71?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=358&q=80
---

# My first blog post

Welcome to my first blog post using nuxt content module.
dsa

## Using HTML into your markdown files

<div class="bg-blue-500 text-white p-4 mb-4">
  This is HTML inside markdown that has a class of note
</div>

## Adding a Vue component

### InfoBox

<info-box>
  <template #info-box>
    This is a vue component inside markdown using slots
  </template>
</info-box>

### Code block

export default {
  nuxt: 'is the best'
}


