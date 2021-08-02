<template>
  <div v-if="posts.length>0">
    <h3>Список Задач</h3>
    <note-item
      v-for="post in posts"
      v-bind:post="post"
      :key="post.id"
      @remove="$emit('remove',post)"
    />
  </div>
  <div v-else>
    <p>Список задач пуст</p>
  </div>
</template>

<script>
import NoteItem from "./NoteItem.vue";

export default {
  components: { NoteItem },
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="css" scoped>
</style>