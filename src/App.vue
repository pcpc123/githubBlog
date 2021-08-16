<template>
  <div id="app">
    <!-- <add-blog> </add-blog> -->
    <!-- <show-blogs> </show-blogs> -->
    <blog-header></blog-header>
    <router-view></router-view>
  </div>
</template>

<script>
import AddBlog from "./components/AddBlog.vue";
import ShowBlogs from "./components/ShowBlogs.vue";
import BlogHeader from "./components/BlogHeader.vue";

export default {
  name: "App",
  components: {
    AddBlog,
    ShowBlogs,
    BlogHeader,
  },
};
</script>

<style>
ul {
  list-style: none;
  text-align: center;
  margin: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #fff;
  text-decoration: none;
  padding: 12px;
  border-radius: 5px;
}

nav {
  background: crimson;
  padding: 30px 0;
  margin-bottom: 40px;
}

.router-link-active {
  background: rgba(255, 255, 255, 0.8);
  color: #444;
}


</style>
