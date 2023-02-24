<template>
  <div>
    <button @click="addLike">likes</button>
    <button @click="addDislike">dislike</button>
    <div>
      Likes <strong>{{ likes }}</strong>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 0,
    };
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.likes -= 1;
    },
  },
};
</script>
<style></style>
