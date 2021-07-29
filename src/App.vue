<template>
  <div>caount like {{ likes }}</div>
  <div>caount dislike{{ dislike }}</div>
  <div>
    <button v-on:click="addLike">like</button>
    <button v-on:click="addDislike">dislike</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      likes: 0,
      dislike: 0,
    };
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislike += 1;
    },
  },
};
</script>
<style>
</style>