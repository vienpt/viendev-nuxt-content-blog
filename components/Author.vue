<template>
  <div>
    <img v-if="author.img" :src="author.img" />
    <div>
      <h4>Author</h4>
      <p>{{ author.name }}</p>
      <p>{{ author.bio }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component({})
export default class Author extends Vue {
  /**
   * write ts style
   */
  @Prop({ required: true }) author!: object

  /**
   * The JavaScript-equivalent code
   * props: {
   *   author: {
   *     type: object,
   *     required: true
   *   }
   * }
   */
}
</script>
