<template>
  <div class="header">
    <img
      src="../image/pencil.png"
      @click='openForm'
    />

  </div>
</template>

<script>
export default {
  data() {},
  methods: {
    openForm() {
      document.querySelector(".forma").classList.toggle("d-none");
    }
  }
};
</script>

<style lang='css' scoped>
.header {
  width: 100%;
  height: 80px;
  background: grey;
}
.header img {
  width: 50px;
  height: 50px;
  margin: 15px;
  cursor: pointer;
  border-radius: 33px;
  transition: 0.4s;
}
.header img:hover {
  transform: rotate(-12deg);
}
.header img:active {
  background: rgba(245, 245, 245, 0.5);
  border: 5px solid rgba(255, 255, 255, 0.432);
  transform: rotate(-28deg);
}
</style>