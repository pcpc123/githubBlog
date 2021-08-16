<template>
  <div id="single-blog">
    <h1>{{ blog.title }}</h1>
    <article>{{ blog.content }}</article>
    <p>作者: {{ blog.author }}</p>
    <p>分类:</p>
    <ul>
      <li v-for="category in blog.categories">
        {{ category }}
      </li>
    </ul>
    <button @click="deleteSingleBlog">删除</button>
    <router-link :to="'/edit/' + id" id="edit">编辑</router-link>
  </div>
</template>

<script>
export default {
  name: "single-blog",
  data() {
    return {
      id: this.$route.params.id,
      blog: {},
    };
  },
  created() {
    this.$http
      .get(
        "https://vuedemo-654bf-default-rtdb.firebaseio.com/posts/" +
          this.id +
          ".json"
      )
      .then(function (data) {
        // console.log(data);
        return data.json();
        // this.blog = data.body;
      })
      .then(function (data) {
        this.blog = data;
      });
  },
  methods: {
    deleteSingleBlog() {
      this.$http
        .delete(
          "https://vuedemo-654bf-default-rtdb.firebaseio.com/posts/" +
            this.id +
            ".json"
        )
        .then((Response) => {
          this.$router.push({ path: "/" });
        });
    },
  },
};
</script>

<style>
#single-blog {
  max-width: 960px;
  margin: 0 auto;
  padding: 20px;
  background-color: #eee;
  border: 1px dotted #aaa;
}

button {
  /* display: block; */
  margin: 20px 0;
  background: crimson;
  color: #fff;
  border: 0;
  padding: 14px;
  border-radius: 4px;
  font-size: 18px;
  cursor: pointer;
}

#edit {
  /* display: inline-block; */
  margin: 20px 0;
  background: crimson;
  color: #fff;
  border: 0;
  padding: 14px;
  border-radius: 4px;
  font-size: 18px;
  cursor: pointer;
  box-sizing: border-box;
  line-height: 18px;
  text-align: center;
  }
</style>