<template>
  <div class="container">
    <h1>Blog Posts</h1>
    <ul>
      <li class="list-disc" v-for="article of articles" :key="article.slug">
        <nuxt-link :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          <img :src="article.img" />
          <div>
            <h2>{{ article.title }}</h2>
            <p>by {{ article.author.name }}</p>
            <p>{{ article.description }}</p>
          </div>
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component({
  async asyncData(ctx) {
    const data = await ctx.app.$content('articles', ctx.params.slug)
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt', 'asc')
      .fetch()
    console.log('data artiles:', data)
    return {
      articles: data
    }
  }
})
export default class Blog extends Vue {
  articles?: any;
}
</script>
