<template>

  <div class="container">
    <header-component /><br>
    <form-create-note-component @create="createPost" />
    <br>
    <note-component
      v-bind:posts='posts'
      @remove="removePost"
    />
  </div>

</template>
<script>
import FormCreateNoteComponent from "./components/FormCreateNoteComponent.vue";
import NoteComponent from "./components/NoteComponent.vue";
import HeaderComponent from "./components/HeaderComponent.vue";

export default {
  components: { FormCreateNoteComponent, NoteComponent, HeaderComponent },
  data() {
    return {
      posts: [
        { id: 1, title: "JS", description: "A b c d e" },
        { id: 2, title: "Node", description: "A b c d e" },
        { id: 3, title: "React", description: "A b c d e" }
      ],
      pts: []
    };
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislike += 1;
    },
    createPost(post) {
      console.log("post", post);
      console.log("post", post.title, post.description);
      this.posts.push(post);
    },
    removePost(post) {
      this.posts.forEach(p => {
        if (p.id != post.id) {
          this.pts.push(p);
        }
      });
      this.posts = this.pts;
      this.pts = [];
    },
    inputTitle(event) {
      this.title = event.target.value;
    },
    inputDescription(event) {
      this.description = event.target.value;
    }
  }
};
</script>
<style>
* {
  padding: 0;
  box-sizing: border-box;
}
.container {
  width: 95%;
  height: 100%;
  max-width: 1200px;
  margin: 0 auto;
  top: 20px;
}

.btn {
  border-radius: 5px;
  margin: 5px 0 5px 30px;
  width: 60px;
}
</style>