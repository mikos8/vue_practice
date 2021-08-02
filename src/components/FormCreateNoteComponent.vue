<template>
  <form
    action=""
    class="forma d-none"
    @submit.prevent
  >

    <h3>Create new Post</h3>
    <input
      v-model="post.title"
      type="text"
      placeholder="Name Post"
      class="input"
    ><br>
    <!--  v-bind:value="post.description"
      @input="post.description = $event.target.value" -->
    <input
      v-model="post.description"
      type="text"
      class="input"
      placeholder="Description Post"
    ><br>
    <button
      @click="addPost"
      class="btn"
    >
      create</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        description: ""
      },
      count: 0
    };
  },
  methods: {
    addPost() {
      if ((this.post.title !== "") & (this.post.description !== "")) {
        this.count += 1;
        this.post.id = this.count;
        this.$emit("create", this.post);
        this.post = { title: "", description: "" };
        document.querySelector(".forma").classList.toggle("d-none");
      }
    }
  }
};
</script>

<style lang='css' scoped>
.forma {
  margin: 10px 30px;
  transition: 0.8s;
}
.forma input {
  margin: 10px 0 10px 30px;
}
.input {
  width: 300px;
  border: 1px solid rgb(6, 104, 6);
  line-height: 24px;
  padding: 5px;
}
.btn {
  color: rgb(255, 255, 255);
  font-size: 16px;
  width: 70px;
  line-height: 24px;
  height: 30px;
  border: none;
  background-color: rgb(93, 196, 124);
  cursor: pointer;
  transition: 0.4s;
}
.btn:hover {
  background-color: rgb(79, 173, 108);
}
.btn:active {
  background-color: rgb(53, 112, 71);
}
.d-none {
  display: none;
}
</style>