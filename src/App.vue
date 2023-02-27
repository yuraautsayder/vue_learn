<template>
  <div>
    <div class="post">
      <div><strong>Название:</strong> пост о JavaSciript</div>
      <div><strong>Описание:</strong> текст о JavaSciript</div>
    </div>
    <div class="post">
      <div><strong>Название:</strong> пост о JavaSciript</div>
      <div><strong>Описание:</strong> текст о JavaSciript</div>
    </div>
    <div class="post">
      <div><strong>Название:</strong> пост о JavaSciript</div>
      <div><strong>Описание:</strong> текст о JavaSciript</div>
    </div>
    <div class="post">
      <div><strong>Название:</strong> пост о JavaSciript</div>
      <div><strong>Описание:</strong> текст о JavaSciript</div>
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
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.post {
  padding: 15px;
  border: 1px solid #efefef;
  margin-top: 15px;
}
</style>
