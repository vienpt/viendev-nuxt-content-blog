<template>
  <div>
    <!-- {{ message }} -->
    <nav>
      <ul>
        <li v-for="link of article.toc" :key="link.id">
          <nuxt-link
            :class="{ 'py-2': link.depth === 2, 'ml-2 pb-2': link.depth === 3 }"
            :to="`#${link.id}`">
            {{ link.text }}
          </nuxt-link>
        </li>
      </ul>
    </nav>
    <article>
      <h1>{{ article.title }}</h1>
      <p>{{ article.description }}</p>
      <img :src="article.img" :alt="article.alt" />
      <p>Article last updated: {{ formatDate(article.updatedAt) }}</p>


      <!-- <pre>{{ article }}</pre> -->
      <nuxt-content :document="article" />

      <author :author="article.author" />

      <prev-next :prev="prev" :next="next" />
    </article>
  </div>
</template>


<script lang="ts">
/**
 * Set lang is 'ts'
 * Using Class API type code
 * Import Class API
 * Condition: install package 'vue-class-component'
 */
import { Component, Vue } from 'vue-property-decorator'

@Component({
  async asyncData(ctx) {
    /**
     * parameter: ctx (context)
     * => nuxt context: https://nuxtjs.org/api/context
     * methods: fetch our article here from $content
     */
    const data = await ctx.app.$content('articles', ctx.params.slug).fetch()
    const [prev, next] = await ctx.app.$content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(ctx.params.slug)
      .fetch()

    return {
      /**
       * assign data to article
       */
      article: data,
      prev: prev,
      next: next
    }
  }
})
export default class BlogPost extends Vue {
  /**
   * Format: variable: type
   * ? => NULL or not NULL
   * */
  // message: string = 'this is class API'
  article?: any
  prev?: object
  next?: object
  ngaygio: string|undefined

  formatDate(date: string) {
    const options = { year: 'numeric', month: 'long', day: 'numeric' }
    return new Date(date).toLocaleDateString('en', options)
  }
}
</script>

<style>
  .nuxt-content h2 {
    font-weight: bold;
    font-size: 28px;
  }
  .nuxt-content h3 {
    font-weight: bold;
    font-size: 22px;
  }
  .nuxt-content p {
    margin-bottom: 20px;
  }
  .icon.icon-link {
    background-image: url('~assets/svg/icon-hashtag.svg');
    display: inline-block;
    width: 20px;
    height: 20px;
    background-size: 20px 20px;
  }
</style>
