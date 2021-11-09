<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Posts :posts="posts"></Posts>
</template>

<script>
import Posts from "./components/Posts.vue";

export default {
  name: "App",
  components: {
    Posts,
  },
  data() {
    return {
      posts: [
        {
          title: "My cool post",
          views: 30,
        },
        {
          title: "Another awesome post",
          views: 23,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
