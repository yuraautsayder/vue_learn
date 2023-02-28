<template>
  <div class="app">
    <div>
      <PostForm @create="createPost" />
      <PostList :posts="posts" />
    </div>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "Пост 1 о JavaScript", body: "текст о JavaScript" },
        { id: 2, title: "Пост 2 о JavaScript", body: "текст о JavaScript" },
        { id: 3, title: "Пост 3 о JavaScript", body: "текст о JavaScript" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
<!-- TIMING 56:28 -->
