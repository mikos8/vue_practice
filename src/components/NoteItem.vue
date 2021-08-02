<template>
  <div class="post">
    <div>
      <img
        class="img-note"
        src="../image/note.png"
        alt=""
      >
    </div>
    <div class="content-note">
      <input
        type="checkbox"
        class="check_item"
        @click="changeCheck"
      ><span>{{post.title}}</span>
      <br>
      {{post.description}}
    </div>
    <div class="btn-option">
      <button
        class="option_item"
        @click="$emit('remove',post)"
      >remove</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  methods: {
    changeCheck() {
      let status = document.querySelector(".check_item").checked;
      let text = document.querySelector(".title-item");
      if (status) {
        console.log(status);
      }
    }
  }
};
</script>

<style lang="css" scoped>
.post {
  margin: 10px 15px;
  padding: 15px;
  border: 1px solid #76c2ce;
  box-shadow: 1px 1px 1px rgba(20, 20, 20, 0.63);
  cursor: pointer;
  border-radius: 5px;
  display: flex;
  transition: border 0.5s ease-in-out;
}
.post:hover {
  border: 1px solid rgba(128, 128, 128, 0.308);
}
.img-note {
  width: 20px;
  height: 20px;
  margin-right: 10px;
  transition: 0.4s;
}
.img-note:hover {
  transform: translate(-2px, 0%);
  transform: scale(1.1, 1.1);
  filter: blur(1px);
}
.post:active {
  background: rgba(197, 197, 197, 0.103);
}
.content-note {
  width: 100%;
  padding: 5px 10px;
}
.btn-option {
  width: 10%;
  position: relative;
}

.option_item {
  width: 70px;
  height: 30px;
  margin: 5px;
  border: none;
  border-radius: 17px;
  background: #03bfc5;
  color: white;
  cursor: pointer;
  opacity: 0.5;
}
.option_item:hover {
  opacity: 0.9;
}
.option_item:active {
  opacity: 1;
}

.option_item:active {
  background: #069499;
}

.check_item:checked + span {
  text-decoration: line-through;
  opacity: 0.6;
}
</style>