<template>
  <button class="post-button"><slot></slot></button>
</template>

<script>
export default {
  name: "my-button",
};
</script>

<style scoped>
.post-button {
  padding: 15px;
}
</style>
